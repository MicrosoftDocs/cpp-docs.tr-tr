---
title: Metin ve dizeler Visual C++'ta | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- programming [C++], international
- multiple language support [C++]
- Unicode [C++]
- international applications [C++], about international applications
- portability [C++]
- translation [C++], character sets
- non-European characters [C++]
- character sets [C++]
- globalization [C++]
- Japanese characters [C++]
- Kanji character support [C++]
- local character sets [C++]
- ASCII characters [C++]
- character sets [C++], about character sets
- localization [C++], character sets
- translating code [C++]
- localization [C++]
- character sets [C++], non-European
- portability [C++], character sets
- MBCS [C++], international programming
ms.assetid: a1bb27ac-abe5-4c6b-867d-f761d4b93205
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a911b3a4547be409047004969043943b54bb2480
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="text-and-strings-in-visual-c"></a>Visual C++'da Metin ve Dizeler
Uluslararası pazarda uygulama geliştirmenin önemli bir yönü, yerel karakter kümeleri yeterli gösterimidir. ASCII karakter kümesi 0x00-0x7F aralıktaki karakterleri tanımlar. ASCII karakter kümesi için 0x00-0x7F aralıktaki karakterleri aynı tanımlayan ve ayrıca genişletilmiş bir karakter 0x80 0xFF değerine kümesini tanımlamak öncelikle Avrupa, diğer karakter kümesi vardır. Bu nedenle, bir 8 bit, tek bayt karakter kümesi (SBCS) ASCII karakter kümesi gibi birçok Avrupa dilleri için karakter kümesi temsil etmek yeterli olur. Ancak, Japonca Kanji gibi bazı Avrupa dışı karakter kümesi tek baytlı kodlama düzeni temsil eder ve bu nedenle çok baytlı karakter kümesi (MBCS) kodlaması gerektiren daha çok daha fazla karakter içerir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Unicode ve MBCS](../text/unicode-and-mbcs.md)  
 Unicode ve MBCS programlama için Visual C++ desteğini açıklar.  
  
 [Unicode Desteği](../text/support-for-unicode.md)  
 Unicode, tek bir bayt ile temsil edilemez karakter kümeleri dahil olmak üzere tüm karakter kümelerini desteklemek için bir belirtimi açıklar.  
  
 [Çok baytlı karakter kümeleri (MBCS) desteği](../text/support-for-multibyte-character-sets-mbcss.md)  
 MBCS, Unicode karakter kümeleri, Japonca ve tek bir bayt ile temsil edilemez Çince gibi desteklemek için bir alternatif açıklanır.  
  
 [Tchar.h'de Genel Metin Eşlemeleri](../text/generic-text-mappings-in-tchar-h.md)  
 Microsoft'a özgü genel metin eşlemeleri birçok veri türleri, yordamlar ve diğer nesneleri sağlar.  
  
 [Nasıl yapılır: Çeşitli Dize Türleri Arasında Dönüştürme Yapma](../text/how-to-convert-between-various-string-types.md)  
 Visual C++ dize çeşitli diğer dizeleri dönüştürülmesi gösterilmektedir.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Uluslararası duruma getirme](../c-runtime-library/internationalization.md)  
 C Çalışma Zamanı Kitaplığı'nda uluslararası destek açıklanır.  
  
 [Uluslararası örnekler](http://msdn.microsoft.com/en-us/aa8d390c-cf4c-4dd8-9dea-74d81f93f2f8)  
 Visual c++ uluslararası gösteren örnekleri içeren bağlantılar sağlar.  
  
 [Dil ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)  
 C Çalışma Zamanı Kitaplığı'nda dili ve ülke/bölge dizeleri sağlar.