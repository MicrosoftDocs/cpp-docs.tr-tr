---
title: Çoklu İş Parçacığı Kullanan Programları Derleme ve Bağlama
ms.date: 11/04/2016
helpviewer_keywords:
- compiling multithreaded programs
- multithreading [C++], linking programs
- threading [C++], linking programs
- multithreading [C++], compiled programs
- threading [C++], compiled programs
- compiling source code [C++], multithread programs
- linking [C++], multithread programs
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
ms.openlocfilehash: bc56c71c4c3c1367d35dd5995054b1d7371ae9de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62236949"
---
# <a name="compiling-and-linking-multithread-programs"></a>Çoklu İş Parçacığı Kullanan Programları Derleme ve Bağlama

Bounce.c programı sunulan [örnek çoklu iş parçacığı kullanan C programı](sample-multithread-c-program.md).

Programları derlenen varsayılan olarak birden çok iş parçacıklı.

### <a name="to-compile-and-link-the-multithread-program-bouncec-from-within-the-development-environment"></a>Derleme ve geliştirme ortamını çoklu iş parçacığı kullanan programda Bounce.c bağlamak için

1. Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.

1. İçinde **proje türleri** bölmesinde tıklayın **Win32**.

1. İçinde **şablonları** bölmesinde tıklayın **Win32 konsol uygulaması**ve ardından Projeyi adlandırın.

1. Projeyi C kaynak kodu içeren bir dosya ekleyin.

1. Üzerinde **derleme** menüsünde tıklayarak projeyi derleyin **derleme** komutu.

### <a name="to-compile-and-link-the-multithread-program-bouncec-from-the-command-line"></a>Derlemek ve komut satırından çoklu iş parçacığı programına Bounce.c bağlamak için

1. Derleme ve programa Bağla:

    ```
    CL BOUNCE.C
    ```

## <a name="see-also"></a>Ayrıca bkz.

[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)
