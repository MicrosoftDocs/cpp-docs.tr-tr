---
title: "Metin ve ikili mod dosyası g-O | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.io
dev_langs: C++
helpviewer_keywords:
- files [C++], open functions
- I/O [CRT], text files
- functions [CRT], file access
- binary access, binary mode file I/O
- translation, modes
- I/O [CRT], binary
- text files, I/O
- I/O [CRT], translation modes
- translation modes (file I/O)
- binary access
ms.assetid: 3196e321-8b87-4609-b302-cd6f3c516051
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0bd2eb90ad8498daa318ffecacd7b32f3f3d3eca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="text-and-binary-mode-file-io"></a>Metin ve İkili Mod Dosyası G/Ç
G/ç işlemleri iki çeviri modları, metin veya ikili dosya açılır moduna birinde gerçekleşir. Veri dosyaları genellikle metin modunda işlenir. Dosya çevirisi modu denetlemek için birini yapabilirsiniz:  
  
-   Geçerli varsayılan ayarı koruyun ve yalnızca seçilen dosyaları açtığınızda alternatif modunu belirtin.  
  
-   İşlevini [_set_fmode](../c-runtime-library/reference/set-fmode.md) açılmış dosyaları için yeni varsayılan modunu değiştirmek için. Kullanım [_get_fmode](../c-runtime-library/reference/get-fmode.md) geçerli varsayılan mod bulunamıyor. Metin modunu ilk varsayılan ayardır (`_O_TEXT`).  
  
-   Doğrudan genel değişkeni ayarlayarak varsayılan çeviri modu değiştirme [_fmode](../c-runtime-library/fmode.md) programınızdaki. İşlev `_set_fmode` Bu değişken, ancak değerini de ayarlanabilir doğrudan ayarlar.  
  
 Çağırdığınızda bir dosyanın açılması işlevi gibi [_kurulum Aç](../c-runtime-library/reference/open-wopen.md), [fopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md), [freopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md), [_fsopen](../c-runtime-library/reference/fsopen-wfsopen.md) veya [_sopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md), geçerli varsayılan ayarı geçersiz kılabilirsiniz `_fmode` işlevine uygun bağımsız değişken belirterek [_set_fmode ](../c-runtime-library/reference/set-fmode.md). `stdin`, `stdout`, Ve `stderr` akışları her zaman varsayılan olarak metin modunda açın; Ayrıca bu varsayılan bu dosyalar açılırken geçersiz kılabilirsiniz. Kullanım [_setmode](../c-runtime-library/reference/setmode.md) dosya açıldıktan sonra dosya tanımlayıcısı kullanılarak çeviri modu değiştirmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Giriş ve çıkış](../c-runtime-library/input-and-output.md)   
 [Kategorilere göre çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)