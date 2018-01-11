---
title: "Çoklu iş parçacığı kullanan programları derleme ve bağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- compiling multithreaded programs
- multithreading [C++], linking programs
- threading [C++], linking programs
- multithreading [C++], compiled programs
- threading [C++], compiled programs
- compiling source code [C++], multithread programs
- linking [C++], multithread programs
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0145c480d74cb1978c1b6caef65489eae96501c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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