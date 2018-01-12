---
title: ". Bağlayıcı girişi olarak obj dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 12/29/2017
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
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9a2896822e97bdbb5ffdf8f869e67beadc1675b7
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="obj-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Obj Dosyaları

Bağlayıcı Aracı (bağlantı. EXE) ortak nesne dosyası biçimi (COFF) olarak .obj dosyaları kabul eder.

## <a name="remarks"></a>Açıklamalar

Microsoft ortak nesne dosya biçimine ilişkin kapsamlı bir açıklama sağlar. Daha fazla bilgi için bkz: [PE biçimi](https://msdn.microsoft.com/library/windows/desktop/ms680547).

## <a name="unicode-support"></a>Unicode desteği

Visual Studio 2005 ile başlayarak, Microsoft Visual C++ Derleyici Unicode karakterler ISO/IEC C ve C++ standartları tarafından tanımlandığı şekilde tanımlayıcıları destekler. Derleyici önceki sürümlerini tanımlayıcılarının yalnızca ASCII karakterleri desteklenir. İşlevler, sınıflar ve istatistikleri adlarında Unicode desteği için derleyici ve bağlayıcı .obj dosyaları COFF sembolleri Unicode UTF-8 kodlamasını kullanın. UTF-8 kodlaması, ASCII Visual Studio'nun önceki sürümleri tarafından kullanılan kodlama ile upwardly uyumludur.

Derleyicide ve bağlayıcıda hakkında daha fazla bilgi için bkz: [derleyicide ve bağlayıcıda Unicode desteği](../../build/reference/unicode-support-in-the-compiler-and-linker.md). Unicode standart hakkında daha fazla bilgi için bkz: [Unicode](http://go.microsoft.com/fwlink/p/?linkid=37123) kuruluş.

## <a name="see-also"></a>Ayrıca bkz.

[LINK Giriş Dosyaları](../../build/reference/link-input-files.md)  
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)  
[Unicode Desteği](../../text/support-for-unicode.md)  
[Derleyicide ve Bağlayıcıda Unicode Desteği](../../build/reference/unicode-support-in-the-compiler-and-linker.md)  
[Unicode standart](http://go.microsoft.com/fwlink/p/?linkid=37123)  
[PE biçimi](https://msdn.microsoft.com/library/windows/desktop/ms680547)  
