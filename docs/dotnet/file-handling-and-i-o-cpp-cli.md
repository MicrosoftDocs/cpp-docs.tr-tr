---
title: Dosya işleme ve g / Ç (C + +/ CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- .NET Framework [C++], file handling
- files [C++], .NET Framework and
- I/O [C++], .NET Framework applications
- .NET Framework [C++], I/O
- files [C++], listing files
- directories [C++], listing files
- monitoring file system events
- FileSystemWatcher class, examples
- examples [C++], monitoring file system changes
- events [C++], monitoring
- file system events [C++]
- files [C++], binary
- binary files, reading in C++
- reading text files
- text files, reading
- files [C++], retrieving information about
- FileInfo class
- binary files, writing in C++
- files [C++], binary
- files [C++], text
- text files, writing in C++
ms.assetid: 3296fd59-a83a-40d4-bd4a-6096cc13101b
ms.openlocfilehash: 697d193f2239d9d22e8d94d479bbf24784e2c6ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585659"
---
# <a name="file-handling-and-io-ccli"></a>Dosya İşleme ve G/Ç (C++/CLI)
.NET Framework kullanan çeşitli dosya işlemlerini gösterir.

Aşağıdaki konular alanında tanımlanan sınıfların kullanımını gösteren <xref:System.IO> dosya işlemleri için çeşitli gerçekleştirmek için ad alanı.

## <a name="enumerate"></a> Bir dizindeki dosyaları numaralandırma

Aşağıdaki kod örneği, bir dizindeki dosyaların bir listesini almak nasıl gösterir. Ayrıca, alt dizinler numaralandırılır. Aşağıdaki kod örneğinde <xref:System.IO.Directory.GetFiles%2A> <xref:System.IO.Directory.GetFiles%2A> ve <xref:System.IO.Directory.GetDirectories%2A> C:\Windows directory içeriğini görüntülemek için yöntemleri.

### <a name="example"></a>Örnek

```cpp
// enum_files.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;

int main()
{
   String^ folder = "C:\\";
   array<String^>^ dir = Directory::GetDirectories( folder );
   Console::WriteLine("--== Directories inside '{0}' ==--", folder);
   for (int i=0; i<dir->Length; i++)
      Console::WriteLine(dir[i]);

   array<String^>^ file = Directory::GetFiles( folder );
   Console::WriteLine("--== Files inside '{0}' ==--", folder);
   for (int i=0; i<file->Length; i++)
      Console::WriteLine(file[i]);

   return 0;
}
```

## <a name="monitor"></a> Dosya sistemi değişikliklerini izleme

Aşağıdaki kod örneğinde <xref:System.IO.FileSystemWatcher> oluşturulan, değiştirilen, silinmiş veya yeniden adlandırılan dosyaya karşılık gelen olaylar için kaydedilecek. Kullanabileceğiniz düzenli aralıklarla yoklama dosyalarda yapılan değişiklikler için bir dizin yerine <xref:System.IO.FileSystemWatcher> bir değişiklik algıladığında olaylarını başlatmak için sınıf.

### <a name="example"></a>Örnek

```cpp
// monitor_fs.cpp
// compile with: /clr
#using <system.dll>

using namespace System;
using namespace System::IO;

ref class FSEventHandler
{
public:
    void OnChanged (Object^ source, FileSystemEventArgs^ e)
    {
        Console::WriteLine("File: {0} {1}",
               e->FullPath, e->ChangeType);
    }
    void OnRenamed(Object^ source, RenamedEventArgs^ e)
    {
        Console::WriteLine("File: {0} renamed to {1}",
                e->OldFullPath, e->FullPath);
    }
};

int main()
{
   array<String^>^ args = Environment::GetCommandLineArgs();

   if(args->Length < 2)
   {
      Console::WriteLine("Usage: Watcher.exe <directory>");
      return -1;
   }

   FileSystemWatcher^ fsWatcher = gcnew FileSystemWatcher( );
   fsWatcher->Path = args[1];
   fsWatcher->NotifyFilter = static_cast<NotifyFilters>
              (NotifyFilters::FileName |
               NotifyFilters::Attributes |
               NotifyFilters::LastAccess |
               NotifyFilters::LastWrite |
               NotifyFilters::Security |
               NotifyFilters::Size );

    FSEventHandler^ handler = gcnew FSEventHandler();
    fsWatcher->Changed += gcnew FileSystemEventHandler(
            handler, &FSEventHandler::OnChanged);
    fsWatcher->Created += gcnew FileSystemEventHandler(
            handler, &FSEventHandler::OnChanged);
    fsWatcher->Deleted += gcnew FileSystemEventHandler(
            handler, &FSEventHandler::OnChanged);
    fsWatcher->Renamed += gcnew RenamedEventHandler(
            handler, &FSEventHandler::OnRenamed);

    fsWatcher->EnableRaisingEvents = true;

    Console::WriteLine("Press Enter to quit the sample.");
    Console::ReadLine( );
}
```

## <a name="read_binary"></a> İkili dosyaları okuma

Aşağıdaki kod örneğinde nasıl iki sınıflarını kullanarak ikili verileri bir dosyadan okunur gösterir <xref:System.IO?displayProperty=fullName> ad alanı: <xref:System.IO.FileStream> ve <xref:System.IO.BinaryReader>. <xref:System.IO.FileStream> gerçek dosyayı temsil eder. <xref:System.IO.BinaryReader> ikili erişime izin veren akış için bir arabirim sağlar.

Kod örneği, data.bin adlı ve ikili biçimde tamsayılar içeren bir dosyayı okur. Bu türdeki dosyalar hakkında daha fazla bilgi için bkz. [nasıl yapılır: ikili dosyaları yazma (C + +/ CLI)](../dotnet/how-to-write-a-binary-file-cpp-cli.md).

### <a name="example"></a>Örnek

```cpp
// binary_read.cpp
// compile with: /clr
#using<system.dll>
using namespace System;
using namespace System::IO;

int main()
{
   String^ fileName = "data.bin";
   try
   {
      FileStream^ fs = gcnew FileStream(fileName, FileMode::Open);
      BinaryReader^ br = gcnew BinaryReader(fs);

      Console::WriteLine("contents of {0}:", fileName);
      while (br->BaseStream->Position < br->BaseStream->Length)
         Console::WriteLine(br->ReadInt32().ToString());

      fs->Close( );
   }
   catch (Exception^ e)
   {
      if (dynamic_cast<FileNotFoundException^>(e))
         Console::WriteLine("File '{0}' not found", fileName);
      else
         Console::WriteLine("Exception: ({0})", e);
      return -1;
   }
   return 0;
}
```

## <a name="read_text"></a> Metin dosyası okuma

Aşağıdaki kod örneği, açın ve kullanarak bir kerede bir metin dosyası bir satırı okumak gösterilmiştir <xref:System.IO.StreamReader> tanımlanan sınıfı <xref:System.IO?displayProperty=fullName> ad alanı. Bu sınıf örneği metin dosyası açmak için kullanılır ve ardından <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName> yöntemi her satırı almak için kullanılır.

Bu kod örneği, textfile.txt adlı ve metin içeren bir dosyayı okur. Bu türdeki dosyalar hakkında daha fazla bilgi için bkz. [nasıl yapılır: metin dosyaları yazma (C + +/ CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md).

### <a name="example"></a>Örnek

```cpp
// text_read.cpp
// compile with: /clr
#using<system.dll>
using namespace System;
using namespace System::IO;

int main()
{
   String^ fileName = "textfile.txt";
   try
   {
      Console::WriteLine("trying to open file {0}...", fileName);
      StreamReader^ din = File::OpenText(fileName);

      String^ str;
      int count = 0;
      while ((str = din->ReadLine()) != nullptr)
      {
         count++;
         Console::WriteLine("line {0}: {1}", count, str );
      }
   }
   catch (Exception^ e)
   {
      if (dynamic_cast<FileNotFoundException^>(e))
         Console::WriteLine("file '{0}' not found", fileName);
      else
         Console::WriteLine("problem reading file '{0}'", fileName);
   }

   return 0;
}
```

## <a name="retrieve"></a> Dosya bilgisi alma

Aşağıdaki kod örneğinde <xref:System.IO.FileInfo> sınıfı. Bir dosya adı varsa, bu sınıf, oluşturma ve son değiştirilme dosyanın dosya boyutu, dizin, tam ad ve tarih ve saat gibi ilgili bilgileri almak için de kullanabilirsiniz.

Bu kod, Notepad.exe dosya bilgilerini alır.

### <a name="example"></a>Örnek

```cpp
// file_info.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;

int main()
{
   array<String^>^ args = Environment::GetCommandLineArgs();
   if (args->Length < 2)
   {
      Console::WriteLine("\nUSAGE : file_info <filename>\n\n");
      return -1;
   }

   FileInfo^ fi = gcnew FileInfo( args[1] );

   Console::WriteLine("file size: {0}", fi->Length );

   Console::Write("File creation date:  ");
   Console::Write(fi->CreationTime.Month.ToString());
   Console::Write(".{0}", fi->CreationTime.Day.ToString());
   Console::WriteLine(".{0}", fi->CreationTime.Year.ToString());

   Console::Write("Last access date:  ");
   Console::Write(fi->LastAccessTime.Month.ToString());
   Console::Write(".{0}", fi->LastAccessTime.Day.ToString());
   Console::WriteLine(".{0}", fi->LastAccessTime.Year.ToString());

   return 0;
}
```

## <a name="write_binary"></a> İkili dosyaları yazma

Aşağıdaki kod örneği, ikili verileri bir dosyaya yazmak gösterir. İki sınıf <xref:System.IO> ad alanı kullanılır: <xref:System.IO.FileStream> ve <xref:System.IO.BinaryWriter>. <xref:System.IO.FileStream> gerçek dosyayı temsil ederken <xref:System.IO.BinaryWriter> ikili erişime izin veren akış için bir arabirim sağlar.

Aşağıdaki kod örneği, ikili biçimde tamsayılar içeren bir dosyasına yazar. Kod ile bu dosyayı okuma [nasıl yapılır: ikili dosyaları okuma (C + +/ CLI)](../dotnet/how-to-read-a-binary-file-cpp-cli.md).

### <a name="example"></a>Örnek

```cpp
// binary_write.cpp
// compile with: /clr
#using<system.dll>
using namespace System;
using namespace System::IO;

int main()
{
   array<Int32>^ data = {1, 2, 3, 10000};

   FileStream^ fs = gcnew FileStream("data.bin", FileMode::Create);
   BinaryWriter^ w = gcnew BinaryWriter(fs);

   try
   {
      Console::WriteLine("writing data to file:");
      for (int i=0; i<data->Length; i++)
      {
         Console::WriteLine(data[i]);
         w->Write(data[i]);
      }
   }
   catch (Exception^)
   {
     Console::WriteLine("data could not be written");
     fs->Close();
     return -1;
   }

   fs->Close();
   return 0;
}
```

## <a name="write_text"></a> Metin dosyaları yazma

Aşağıdaki kod örneği, bir metin dosyası oluşturun ve metin kullanarak yazmak gösterilmiştir <xref:System.IO.StreamWriter> sınıfı içinde tanımlanan <xref:System.IO> ad alanı. <xref:System.IO.StreamWriter> Oluşturucusu oluşturulacak dosyanın adını alır. Dosya varsa, üzerine yazılır (True saniye geçirmediğiniz sürece <xref:System.IO.StringWriter> oluşturucu bağımsız değişkeni).

Dosya, ardından kullanarak dosyalanır <xref:System.IO.StreamWriter.Write%2A> ve <xref:System.IO.TextWriter.WriteLine%2A> işlevleri.

### <a name="example"></a>Örnek

```cpp
// text_write.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;

int main()
{
   String^ fileName = "textfile.txt";

   StreamWriter^ sw = gcnew StreamWriter(fileName);
   sw->WriteLine("A text file is born!");
   sw->Write("You can use WriteLine");
   sw->WriteLine("...or just Write");
   sw->WriteLine("and do {0} output too.", "formatted");
   sw->WriteLine("You can also send non-text objects:");
   sw->WriteLine(DateTime::Now);
   sw->Close();
   Console::WriteLine("a new file ('{0}') has been written", fileName);

   return 0;
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

[Dosya ve Stream g / Ç](/dotnet/standard/io/index)

[System.IO ad alanı](https://msdn.microsoft.com/library/system.io.aspx)