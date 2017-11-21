---
title: "Nasıl yapılır: ikili dosyaları okuma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- files [C++], binary
- binary files, reading in C++
ms.assetid: 41ad9ad1-5cac-489c-874e-4bb3a649073a
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 894332d7d63bc5a7c8d4ff701061c1ad15cd1e03
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-read-a-binary-file-ccli"></a>Nasıl yapılır: İkili Dosyaları Okuma (C++/CLI)
Aşağıdaki kod örneği, iki sınıflardan kullanarak bir dosyadan ikili veri okumaya gösterilmiştir <xref:System.IO?displayProperty=fullName> ad alanı: <xref:System.IO.FileStream> ve <xref:System.IO.BinaryReader>. <xref:System.IO.FileStream>gerçek dosyayı temsil eder. <xref:System.IO.BinaryReader>ikili erişimi sağlayan akışa bir arabirim sağlar.  
  
 Kod örneği data.bin adlandırılmış ve ikili biçimde tamsayılar içeren bir dosyayı okur. Bu tür dosyaları hakkında daha fazla bilgi için bkz: [nasıl yapılır: ikili dosyaları yazma (C + +/ CLI)](../dotnet/how-to-write-a-binary-file-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya ve akış t-O](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)