---
title: Input string mode text di java
layout: post
---

Mengawali awal bulan februari ini, saya mencoba belajar input data menggunakan java dengan menggunakan lanterna mode text sebagai library nya berikut ini scriptnya:

~~~~~
package com.example;

import com.googlecode.lanterna.TerminalSize;
import com.googlecode.lanterna.TextColor;
import com.googlecode.lanterna.graphics.TextGraphics;
import com.googlecode.lanterna.input.KeyStroke;
import com.googlecode.lanterna.input.KeyType;
import com.googlecode.lanterna.screen.Screen;
import com.googlecode.lanterna.screen.TerminalScreen;
import com.googlecode.lanterna.terminal.DefaultTerminalFactory;
import com.googlecode.lanterna.terminal.Terminal;

import java.io.IOException;

public class App {
    public static void main(String[] args) {
        try {
            // Inisialisasi terminal
            Terminal terminal = new DefaultTerminalFactory().createTerminal();
            Screen screen = new TerminalScreen(terminal);
            screen.startScreen();

            // Inisialisasi grafik teks
            TextGraphics textGraphics = screen.newTextGraphics();

            // Meminta pengguna untuk memasukkan string
            System.out.print("Masukkan sebuah string: ");
            String inputString = readStringFromUser(screen);

            // Tampilkan string di layar
            TextColor greenColor = TextColor.ANSI.GREEN;
            TextColor blackColor = TextColor.ANSI.BLACK;

            // Posisi tengah layar
            int xPosition = (screen.getTerminalSize().getColumns() - inputString.length()) / 2;
            int yPosition = screen.getTerminalSize().getRows() / 2;

            for (int i = 0; i < inputString.length(); i++) {
                textGraphics.setForegroundColor(greenColor);
                textGraphics.setBackgroundColor(blackColor);
                textGraphics.putString(xPosition + i, yPosition, String.valueOf(inputString.charAt(i)));
                screen.refresh();  // Perbarui layar setiap karakter dimasukkan
                Thread.sleep(100); // Tunggu sejenak agar karakter dapat terlihat
            }

            // Tunggu sejenak setelah memasukkan seluruh string
            Thread.sleep(2000);

            // Tutup layar
            screen.close();
        } catch (IOException | InterruptedException e) {
            e.printStackTrace();
        }
    }

    // Metode untuk membaca string dari pengguna menggunakan lanterna
    private static String readStringFromUser(Screen screen) throws IOException, InterruptedException {
        StringBuilder inputStringBuilder = new StringBuilder();

        while (true) {
            KeyStroke keyStroke = screen.readInput();

            if (keyStroke.getKeyType() == KeyType.Enter) {
                break;
            } else if (keyStroke.getKeyType() == KeyType.Character) {
                char inputChar = keyStroke.getCharacter();
                inputStringBuilder.append(inputChar);

                // Tampilkan karakter yang dimasukkan
                System.out.print(inputChar);
            }
        }

        return inputStringBuilder.toString();
    }
}
~~~~~~~~~~~~~~~~~~