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
ms.openlocfilehash: 5df81fa3d47005fc80bdb3b1c78cba050775cda6
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42465535"
---
# <a name="compiling-and-linking-multithread-programs"></a>Çoklu İş Parçacığı Kullanan Programları Derleme ve Bağlama
Bounce.c programı sunulan [örnek çoklu iş parçacığı kullanan C programı](../parallel/sample-multithread-c-program.md).  
  
Programları derlenen varsayılan olarak birden çok iş parçacıklı.  
  
### <a name="to-compile-and-link-the-multithread-program-bouncec-from-within-the-development-environment"></a>Derleme ve geliştirme ortamını çoklu iş parçacığı kullanan programda Bounce.c bağlamak için  
  
1.  Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.  
  
2.  İçinde **proje türleri** bölmesinde tıklayın **Win32**.  
  
3.  İçinde **şablonları** bölmesinde tıklayın **Win32 konsol uygulaması**ve ardından Projeyi adlandırın.  
  
4.  Projeyi C kaynak kodu içeren bir dosya ekleyin.  
  
5.  Üzerinde **derleme** menüsünde tıklayarak projeyi derleyin **derleme** komutu.  
  
### <a name="to-compile-and-link-the-multithread-program-bouncec-from-the-command-line"></a>Derlemek ve komut satırından çoklu iş parçacığı programına Bounce.c bağlamak için  
  
1.  Derleme ve programa Bağla:  
  
    ```  
    CL BOUNCE.C  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.

[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-c-and-win32.md)