---
title: execution_character_set | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
dev_langs: C++
helpviewer_keywords: pragma execution_character_set
ms.assetid: 32248cbc-7c92-4dca-8442-230c052b53ad
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aaca2dde4bd4f3109828781f761f688a01eee512
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="executioncharacterset"></a>execution_character_set
Dize ve karakter değişmez değerleri için kullanılan yürütme karakter kümesini belirtir. Bu yönerge u8 öneki ile işaretlenmiş değişmez değerleri için gerekli değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma execution_character_set("target")  
```  
  
#### <a name="parameters"></a>Parametreler  
 `target`  
 Hedef yürütme karakter kümesini belirtir. Şu anda desteklenen ayarlamak yalnızca hedef yürütmesi "utf-8" dir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu derleme yönergesi, Visual Studio 2015 güncelleştirme 2'de başlangıç kullanılmıyor. Kullanmanızı öneririz **/execution-charset:utf-8** veya **/utf-8** derleyici seçenekleri kullanarak birlikte `u8` ön ekini temel genişletilmiş içeren dar karakter ve dize değişmez değerleri karakter. Hakkında daha fazla bilgi için `u8` önek, bkz: [dize ve karakter değişmez değerleri](../cpp/string-and-character-literals-cpp.md). Derleyici seçenekleri hakkında daha fazla bilgi için bkz: [/execution-charset (ayarlamak yürütme karakter kümesi)](../build/reference/execution-charset-set-execution-character-set.md) ve [/utf-8 (kaynağı Ayarla ve UTF-8 kümelerine karakter yürütülebilir)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md).  
  
 `#pragma execution_character_set("utf-8")` Yönergesi dar karakter ve kaynak kodunuzdaki dar dize değişmez değerleri yürütülebilir dosya UTF-8 olarak kodlanacak derleyici söyler. Bu çıktı kodlama, kaynak dosya kullanılan kodlama bağımsızdır.  
  
 Varsayılan olarak, yürütme karakter kümesi geçerli kod sayfasını kullanarak dar karakterler ve dar dizeleri derleyici kodlar. Bu, geçerli kod sayfası aralığın dışında olan Unicode DBCS karakter veya bir hazır değer çıktıda varsayılan değiştirme karakteri dönüştürülür anlamına gelir. Unicode ve DBCS karakterler kendi düşük düzey bayt kesiliyor. Neredeyse kesinlikle değil ne düşündüğünüz budur. Kullanarak kaynak dosyasında değişmez değerleri için UTF-8 kodlaması belirtebilirsiniz bir `u8` öneki. Derleyici bu UTF-8 ile kodlanmış dize değişmeden çıkış geçirir. Bir bayt U8 kullanarak önekli dar karakter değişmez değerleri sığması gerekir veya Çıkışta kesilir.  
  
 Varsayılan olarak, Visual Studio çıktı için kaynak kodu yorumlamak için kullanılan kaynak karakter kümesi olarak geçerli kod sayfası kullanır. İçinde bir dosyayı okurken Visual Studio, geçerli kod sayfasına göre dosya kod sayfası ayarlamadıysanız veya UTF-16 karakter veya bir bayt sırası işareti (BOM) dosyasının başında algılanan sürece yorumlar. Otomatik algılama UTF-8 bir ürün reçetesi olmadan olarak kodlanmış kaynak dosyalarını karşılaştığında, geçerli kod sayfası UTF-8 ayarlanamıyor çünkü bunlar geçerli kod sayfası kullanılarak kodlanır Visual Studio varsayar. Kod sayfası derleyici uyarıları ve hataları neden olabilir aralığın dışında belirtilen ya da otomatik olarak algılanan karakter kaynak dosya.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [/Execution-Charset (ayarlamak yürütme karakter kümesi)](../build/reference/execution-charset-set-execution-character-set.md)   
 [/UTF-8 (kaynağı Ayarla ve yürütülebilir karakter kümelerini UTF-8)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)