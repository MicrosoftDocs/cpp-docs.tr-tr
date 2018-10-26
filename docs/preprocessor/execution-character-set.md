---
title: execution_character_set | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
dev_langs:
- C++
helpviewer_keywords:
- pragma execution_character_set
ms.assetid: 32248cbc-7c92-4dca-8442-230c052b53ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b81832ba31fc8ef36510ce4f35c9fb1a5f3426b9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075027"
---
# <a name="executioncharacterset"></a>execution_character_set

Dize ve karakter değişmez değerleri için kullanılan yürütme karakter kümesini belirtir. Bu yönerge u8 öneki ile işaretlenmiş bir sabit değerleri için gerekli değildir.

## <a name="syntax"></a>Sözdizimi

```
#pragma execution_character_set("target")
```

### <a name="parameters"></a>Parametreler

*Hedef*<br/>
Hedef yürütme karakter kümesini belirtir. Şu anda desteklenen ayarlama yalnızca hedef yürütme "utf-8" dir.

## <a name="remarks"></a>Açıklamalar

Bu derleyici yönergesi Visual Studio 2015 güncelleştirme 2'de başlayarak kullanımdan kalkmıştır. Kullanmanızı öneririz `/execution-charset:utf-8` veya `/utf-8` derleyici seçeneklerini kullanarak birlikte `u8` genişletilmiş karakterler içeren dar karakter ve dize değişmez değerleri öneki. Hakkında daha fazla bilgi için `u8` önek, bkz: [dize ve karakter değişmez değerleri](../cpp/string-and-character-literals-cpp.md). Derleyici seçenekleri hakkında daha fazla bilgi için bkz. [/Execution-Charset (yürütme karakter kümesini Ayarla)](../build/reference/execution-charset-set-execution-character-set.md) ve [/UTF-8 (kaynak ayarlayın ve yürütülebilir karakter kümelerini UTF-8)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md).

`#pragma execution_character_set("utf-8")` Dar karakter ve dar dize değişmez değerleri, kaynak kodunuzdaki UTF-8 yürütülebilir dosya kodlamak için derleyici yönergesi söyler. Bu çıkış kodlama, kaynak dosya kullanılan kodlama bağımsızdır.

Varsayılan olarak, yürütme karakter kümesi geçerli kod sayfasını kullanarak dar karakter ve dar dizeleri derleyici kodlar. Bu, geçerli kod sayfası aralığın dışında kalan Unicode veya DBCS karakter değişmez değer olarak çıktı varsayılan değiştirme karakteri dönüştürülür anlamına gelir. Unicode ve DBCS karakterler, düşük düzey bayta kesilir. Neredeyse kesindir değil ne düşündüğünüz budur. Kullanarak kaynak dosyadaki sabit değerleri için UTF-8 kodlamasını belirtebilirsiniz bir `u8` önek. Derleyici bu UTF-8 olarak kodlanmış dizeler değiştirilmemiş çıkışı geçirir. Bir bayt U8 kullanılarak öneklenmemiştir dar karakter değişmez değerleri uygun olmalıdır veya çıktı kesirli kısmı.

Varsayılan olarak, Visual Studio, kaynak kodunuz için çıkış yorumlamak için kullanılan kaynak karakter kümesi olarak geçerli kod sayfası kullanır. Bir dosya içinde okunduğunda, Visual Studio, geçerli kod sayfasına göre dosya kod sayfası ayarlamadıysanız veya dosyanın başında bayt sırası işareti (BOM) ya da UTF-16 karakter algılanan sürece yorumlar. Otomatik algılama kaynak dosyaları içermeyen bir ürün reçetesi UTF-8 olarak kodlanmış karşılaştığında geçerli kod sayfası UTF-8 olarak ayarlanamıyor çünkü Visual Studio, geçerli kod sayfası kullanılarak kodlanır varsayar. Kod sayfası Derleyici uyarılarını ve hataları neden aralığı dışında belirtilen veya otomatik olarak algılanan karakter kaynak dosyası.

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma yönergeleri ve \_ \_Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[/ Execution-Charset (yürütme karakter kümesini Ayarla)](../build/reference/execution-charset-set-execution-character-set.md)<br/>
[/utf-8 (Kaynak ve Yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)