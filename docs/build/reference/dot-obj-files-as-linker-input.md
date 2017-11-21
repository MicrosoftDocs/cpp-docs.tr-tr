---
title: ". Bağlayıcı girişi olarak obj dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
ms.assetid: 3028e423-8b10-4972-8eb4-6e9ae58f0a26
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ca8346f9ff29d097450eda4d8bfbfee7f7a3f522
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="obj-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Obj Dosyaları
Bağlayıcı Aracı (bağlantı. EXE) ortak nesne dosyası biçimi (COFF) olarak .obj dosyaları kabul eder.  
  
## <a name="remarks"></a>Açıklamalar  
 Microsoft ortak nesne dosyasının biçimini tanımlayan indirilebilir bir belge sağlar. Daha fazla bilgi için düzeltme 8.1 veya sonraki karşıdan [Microsoft taşınabilir yürütülebilir ve ortak nesne dosya biçimi belirtimlerine](http://go.microsoft.com/fwlink/?LinkId=93292).  
  
## <a name="unicode-support"></a>Unicode Desteği  
 Visual Studio 2005 ile başlayarak, Microsoft Visual C++ Derleyici Unicode karakterler ISO/IEC C ve C++ standartları tarafından tanımlandığı şekilde tanımlayıcıları destekler. Derleyici önceki sürümlerini tanımlayıcılarının yalnızca ASCII karakterleri desteklenir. İşlevler, sınıflar ve istatistikleri adlarında Unicode desteği için derleyici ve bağlayıcı .obj dosyaları COFF sembolleri Unicode UTF-8 kodlamasını kullanın. UTF-8 kodlaması, ASCII Visual Studio'nun önceki sürümleri tarafından kullanılan kodlama ile upwardly uyumludur.  
  
 Derleyicide ve bağlayıcıda hakkında daha fazla bilgi için bkz: [derleyicide ve bağlayıcıda Unicode desteği](../../build/reference/unicode-support-in-the-compiler-and-linker.md). Unicode standart hakkında daha fazla bilgi için bkz: [Unicode](http://go.microsoft.com/fwlink/?LinkId=37123) kuruluş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINK giriş dosyaları](../../build/reference/link-input-files.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
 [Unicode desteği](../../text/support-for-unicode.md)   
 [Derleyicide ve bağlayıcıda Unicode desteği](../../build/reference/unicode-support-in-the-compiler-and-linker.md)   
 [Unicode standart](http://go.microsoft.com/fwlink/?LinkId=37123)   
 [Genel nesne dosya biçimi belirtimlerine](http://go.microsoft.com/fwlink/?LinkId=93292)