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
ms.workload: cplusplus
ms.openlocfilehash: 50387aa2512e38a4e9f13fdfb1b042c3df2de45c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="text-and-binary-mode-file-io"></a>Metin ve İkili Mod Dosyası G/Ç
G/ç işlemleri iki çeviri modları, metin veya ikili dosya açılır moduna birinde gerçekleşir. Veri dosyaları genellikle metin modunda işlenir. Dosya çevirisi modu denetlemek için birini yapabilirsiniz:  
  
-   Geçerli varsayılan ayarı koruyun ve yalnızca seçilen dosyaları açtığınızda alternatif modunu belirtin.  
  
-   İşlevini [_set_fmode](../c-runtime-library/reference/set-fmode.md) açılmış dosyaları için yeni varsayılan modunu değiştirmek için. Kullanım [_get_fmode](../c-runtime-library/reference/get-fmode.md) geçerli varsayılan mod bulunamıyor. Metin modunu ilk varsayılan ayardır (`_O_TEXT`).  
  
-   Doğrudan genel değişkeni ayarlayarak varsayılan çeviri modu değiştirme [_fmode](../c-runtime-library/fmode.md) programınızdaki. İşlev `_set_fmode` Bu değişken, ancak değerini de ayarlanabilir doğrudan ayarlar.  
  
 Çağırdığınızda bir dosyanın açılması işlevi gibi [_kurulum Aç](../c-runtime-library/reference/open-wopen.md), [fopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md), [freopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md), [_fsopen](../c-runtime-library/reference/fsopen-wfsopen.md) veya [_sopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md), geçerli varsayılan ayarı geçersiz kılabilirsiniz `_fmode` işlevine uygun bağımsız değişken belirterek [_set_fmode ](../c-runtime-library/reference/set-fmode.md). `stdin`, `stdout`, Ve `stderr` akışları her zaman varsayılan olarak metin modunda açın; Ayrıca bu varsayılan bu dosyalar açılırken geçersiz kılabilirsiniz. Kullanım [_setmode](../c-runtime-library/reference/setmode.md) dosya açıldıktan sonra dosya tanımlayıcısı kullanılarak çeviri modu değiştirmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Giriş ve çıkış](../c-runtime-library/input-and-output.md)   
 [Kategorilere Göre Çalışma Zamanı Yordamları](../c-runtime-library/run-time-routines-by-category.md)