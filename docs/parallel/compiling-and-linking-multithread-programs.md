---
title: Çoklu iş parçacığı kullanan programları derleme ve bağlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- compiling multithreaded programs
- multithreading [C++], linking programs
- threading [C++], linking programs
- multithreading [C++], compiled programs
- threading [C++], compiled programs
- compiling source code [C++], multithread programs
- linking [C++], multithread programs
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0c77cb217fe841e15f4c7470340bd3fbb502f6a9
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="compiling-and-linking-multithread-programs"></a>Çoklu İş Parçacığı Kullanan Programları Derleme ve Bağlama
Bounce.c programı sunulan [örnek çoklu iş parçacığı kullanan C programı](../parallel/sample-multithread-c-program.md).  
  
 Programları derlenen varsayılan olarak birden çok iş parçacıklı.  
  
#### <a name="to-compile-and-link-the-multithread-program-bouncec-from-within-the-development-environment"></a>Çoklu iş parçacığı Bounce.c programını geliştirme ortamında derlemek ve bağlamak için  
  
1.  Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.  
  
2.  İçinde **proje türleri** bölmesinde tıklatın **Win32**.  
  
3.  İçinde **şablonları** bölmesinde tıklatın **Win32 konsol uygulaması**ve projeyi adlandırın.  
  
4.  Projeye C kaynak kodunu içeren dosyayı ekleyin.  
  
5.  Üzerinde **yapı** menüsünde tıklayarak Projeyi derlemek **yapı** komutu.  
  
#### <a name="to-compile-and-link-the-multithread-program-bouncec-from-the-command-line"></a>Çoklu iş parçacığı Bounce.c programını komut satırından derlemek ve bağlamak için  
  
1.  Derleme ve program Bağla:  
  
    ```  
    CL BOUNCE.C  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C ve Win32 ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-c-and-win32.md)