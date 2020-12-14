---
description: 'Daha fazla bilgi edinin: dosya Işleme ve g/ç (C++/CLı)'
title: Dosya İşleme ve G-Ç (C++/CLI)
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
ms.openlocfilehash: 30bcec27cf3bc625554ad55bd7657c156e5409d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252174"
---
# <a name="file-handling-and-io-ccli"></a>Dosya İşleme ve G/Ç (C++/CLI)

.NET Framework kullanarak çeşitli dosya işlemlerini gösterir.

Aşağıdaki konularda <xref:System.IO> çeşitli dosya işlemlerini gerçekleştirmek için ad alanında tanımlanan sınıfların kullanımı gösterilmektedir.

## <a name="enumerate-files-in-a-directory"></a><a name="enumerate"></a> Dizindeki dosyaları listeleme

Aşağıdaki kod örneği, bir dizindeki dosyaların listesinin nasıl alınacağını gösterir. Ayrıca, alt dizinler numaralandırılır. Aşağıdaki kod örneği, <xref:System.IO.Directory.GetFiles%2A> <xref:System.IO.Directory.GetFiles%2A> <xref:System.IO.Directory.GetDirectories%2A> C:\Windows dizininin içeriğini göstermek için ve yöntemlerini kullanır.

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

## <a name="monitor-file-system-changes"></a><a name="monitor"></a> Dosya sistemi değişikliklerini izleme

Aşağıdaki kod örneği <xref:System.IO.FileSystemWatcher> oluşturulan, değiştirilen, silinen veya yeniden adlandırılan dosyalara karşılık gelen olaylara kaydolmak için kullanır. Dosyalarda yapılan değişiklikler için düzenli aralıklarla bir dizin yoklamak yerine, <xref:System.IO.FileSystemWatcher> bir değişiklik algılandığında olayları tetiklemesi için sınıfını kullanabilirsiniz.

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

## <a name="read-a-binary-file"></a><a name="read_binary"></a> Ikili dosyayı oku

Aşağıdaki kod örneği, ad alanından iki sınıf kullanarak bir dosyadan ikili verilerin nasıl okunacağını gösterir <xref:System.IO?displayProperty=fullName> : <xref:System.IO.FileStream> ve <xref:System.IO.BinaryReader> . <xref:System.IO.FileStream> gerçek dosyayı temsil eder. <xref:System.IO.BinaryReader> akış için ikili erişime izin veren bir arabirim sağlar.

Kod örneği, Data. bin adlı bir dosyayı okur ve ikili biçimde tamsayılar içerir. Bu dosya türü hakkında daha fazla bilgi için bkz. [nasıl yapılır: yazma bir Ikili dosya (C++/CLI)](#write_binary).

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

## <a name="read-a-text-file"></a><a name="read_text"></a> Metin dosyası okuma

Aşağıdaki kod örneği, <xref:System.IO.StreamReader> ad alanında tanımlanan sınıfını kullanarak bir metin dosyasının bir kerede bir satırı nasıl açıp okuyabileceğinizi gösterir <xref:System.IO?displayProperty=fullName> . Bu sınıfın bir örneği bir metin dosyası açmak için kullanılır ve ardından <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName> her satırı almak için yöntemi kullanılır.

Bu kod örneği, textfile.txt adlı ve metin içeren bir dosyayı okur. Bu dosya türü hakkında daha fazla bilgi için bkz. [nasıl yapılır: yazma metin dosyası (C++/CLI)](#write_text).

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

## <a name="retrieve-file-information"></a><a name="retrieve"></a> Dosya bilgilerini al

Aşağıdaki kod örneği, sınıfını göstermektedir <xref:System.IO.FileInfo> . Bir dosyanın adına sahip olduğunuzda dosya boyutu, dizin, tam ad ve oluşturma tarihi ve son değişikliğin tarih ve saati gibi bilgileri almak için bu sınıfı kullanabilirsiniz.

Bu kod Notepad.exe için dosya bilgilerini alır.

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

## <a name="write-a-binary-file"></a><a name="write_binary"></a> Ikili dosya yaz

Aşağıdaki kod örneği, bir dosyaya ikili veri yazmayı gösterir. Ad alanındaki iki sınıf <xref:System.IO> kullanılır: <xref:System.IO.FileStream> ve <xref:System.IO.BinaryWriter> . <xref:System.IO.FileStream> gerçek dosyayı temsil ederken, <xref:System.IO.BinaryWriter> akış için ikili erişime izin veren bir arabirim sağlar.

Aşağıdaki kod örneği, ikili biçimde tamsayılar içeren bir dosya yazar. Bu dosya, [nasıl yapılır: bir Ikili dosyayı okuma (C++/CLI)](#read_binary)içindeki kodla okunabilir.

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

## <a name="write-a-text-file"></a><a name="write_text"></a> Metin dosyası yaz

Aşağıdaki kod örneği, bir metin dosyasının nasıl oluşturulacağını ve <xref:System.IO.StreamWriter> ad alanında tanımlanan sınıfını kullanarak buna nasıl metin yazılacağını gösterir <xref:System.IO> . <xref:System.IO.StreamWriter>Oluşturucu oluşturulacak dosyanın adını alır. Dosya varsa, üzerine yazılır (doğru ikinci Oluşturucu bağımsız değişkeni olarak geçmediğiniz sürece <xref:System.IO.StringWriter> ).

Daha sonra dosya <xref:System.IO.StreamWriter.Write%2A> ve işlevleri kullanılarak dosyalanır <xref:System.IO.TextWriter.WriteLine%2A> .

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

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
[Dosya ve akış g/ç](/dotnet/standard/io/index)<br/>
[System.IO ad alanı](/dotnet/api/system.io)
