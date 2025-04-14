# quiz-oak

![Screenshot 2025-04-14 142348](https://github.com/user-attachments/assets/bf6483aa-6906-4462-b996-e9cfca4a48ee)

# Penjelasan Kode :

# Struktur Utama Program

# SECTION.Data

section .data

    message db 'Hello, world!', 0x0A ; Pesan yang akan ditampilkan

1. Bagian .data digunakan untuk menyimpan data statis.

2. message adalah variabel yang berisi string 'Hello, world!' diikuti oleh 0x0A (newline/enter).

3. db (define byte) menyatakan bahwa data disimpan dalam satuan byte.

 # SECTION.TEXT
 
section .text

global _start  ; Menyatakan bahwa _start adalah entry point

1.Bagian .text berisi kode program.

2.global _start memberi tahu linker bahwa _start adalah titik masuk (entry point) dari program.

#ENTRY POINT start

Bagian .text berisi kode program.

global _start memberi tahu linker bahwa _start adalah titik masuk (entry point) dari program.

1.Program dimulai dari _start.

2.mov eax, message menyimpan alamat dari string ke dalam register EAX.

3.call sprint memanggil fungsi sprint untuk mencetak pesan ke layar.

4.call quit memanggil fungsi quit untuk keluar dari program.

#FUNGSI slen — Menghitung Panjang String

slen:
    push ebx           ; Simpan nilai EBX
    mov ebx, eax       ; EBX = alamat awal string

nextchar:
    cmp byte [eax], 0  ; Bandingkan isi alamat EAX dengan null terminator
    jz finish          ; Jika ketemu null (0), selesai
    inc eax            ; Geser ke karakter berikutnya
    jmp nextchar       ; Ulangi pemeriksaan

finish:
    sub eax, ebx       ; Kurangi EAX (akhir string) dengan EBX (awal) → panjang string
    pop ebx            ; Ambil kembali nilai EBX
    ret                ; Kembali ke pemanggil






