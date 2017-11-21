---
title: "-Zc: auto (değişken türünü) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Zc:auto
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 33804c3876d378fe8138795b78a26f36a52e3c96
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto (Değişken Türünü Türet)
**/Zc:auto [-]** derleyici seçeneği derleyici nasıl kullanılacağını söyler [anahtar sözcüğü otomatik](../../cpp/auto-keyword.md) değişkenleri bildirmek için. Varsayılan seçenek belirtirseniz, **/Zc:auto**, derleyici, başlatma ifadesinden bildirilen değişkeninin türü deduces. Belirtirseniz **/Zc:auto-**, otomatik depolama sınıfı değişkenine derleyici ayırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Zc:auto[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 C++ standart bir özgün ve için yeniden düzenlenen bir anlam tanımlar `auto` anahtar sözcüğü. Önce [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], anahtar sözcüğü otomatik depolama sınıfı bir değişkende bildirir; diğer bir deyişle, yerel bir yaşam süresi sahip bir değişken. İle başlayarak [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], anahtar sözcüğü bir değişken bildirimi 's başlatma ifadesinden türünü deduces. Kullanmak **/Zc:auto [-]** özgün ya da düzeltilmiş anlamını kullanmak için derleyicisi bildirmek için derleyici seçeneği `auto` anahtar sözcüğü.  
  
 Derleyici, uygun bir tanılama iletisi verir kullanımınız `auto` anahtar sözcüğü geçerli derleyici seçeneği çelişir. Daha fazla bilgi için bkz: [anahtar sözcüğü otomatik](../../cpp/auto-keyword.md). Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio'da Bu derleyici seçeneği ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **yapılandırma özellikleri** düğümü.  
  
3.  Tıklatın **C/C++** düğümü.  
  
4.  Tıklatın **komut satırı** düğümü.  
  
5.  Ekleme **/Zc:auto** veya **/Zc:auto-** için **ek seçenekler:** bölmesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ZC (Uyumluluk)](../../build/reference/zc-conformance.md)   
 [Auto anahtar sözcüğü](../../cpp/auto-keyword.md)