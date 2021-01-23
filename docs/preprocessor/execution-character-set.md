---
description: pragmaMicrosoft C/C++ ' da execution_character_set yönergesi hakkında daha fazla bilgi edinin
title: execution_character_set pragma
ms.date: 01/22/2021
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
helpviewer_keywords:
- pragma, execution_character_set
- execution_character_set pragma
no-loc:
- pragma
ms.openlocfilehash: cc768aa0d35fffc9c387b31870adf47f35073f35
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712862"
---
# <a name="execution_character_set-no-locpragma"></a>`execution_character_set` pragma

Dize ve karakter değişmez değerleri için kullanılan yürütme karakter kümesini belirtir. Bu yönerge, önekiyle işaretlenmiş sabit değerler için gerekli değildir `u8` .

## <a name="syntax"></a>Syntax

> **`#pragma execution_character_set(`** "*hedef*" **`)`**

### <a name="parameters"></a>Parametreler

*hedef*\
Hedef yürütme karakter kümesini belirtir. Şu anda desteklenen tek hedef yürütme kümesi "UTF-8" dır.

## <a name="remarks"></a>Açıklamalar

Bu derleyici yönergesi Visual Studio 2015 güncelleştirme 2 ' den itibaren kullanımdan kalkmıştır. Ve **`/execution-charset:utf-8`** **`/utf-8`** `u8` genişletilmiş karakterler içeren dize sabit değerleri ve dar karakter üzerinde ön eki kullanarak, veya derleyici seçeneklerini kullanmanızı öneririz. Ön ek hakkında daha fazla bilgi için `u8` bkz. [dize ve karakter sabit değerleri](../cpp/string-and-character-literals-cpp.md). Derleyici seçenekleri hakkında daha fazla bilgi için bkz. [ `/execution-charset` (yürütme karakter kümesini Ayarla)](../build/reference/execution-charset-set-execution-character-set.md) ve [ `/utf-8` (kaynak ve yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md).

`#pragma execution_character_set("utf-8")`Yönergesi derleyiciye, kaynak kodunuzda dar karakter ve dar dize sabit değerlerini yürütülebilir dosyada UTF-8 olarak kodlamasını söyler. Bu çıkış kodlaması kullanılan kaynak dosya kodlamasından bağımsızdır.

Varsayılan olarak, derleyici, geçerli kod sayfasını yürütme karakter kümesi olarak kullanarak dar karakterleri ve dar dizeleri kodluyor. Bu, geçerli kod sayfasının dışındaki Unicode veya DBCS karakterlerinin çıktıda varsayılan değiştirme karakterine dönüştürüldüğü anlamına gelir. Unicode ve DBCS karakterleri düşük sıralı baytlarına kesilir. Bu, neredeyse hiç istemediğiniz bir şeydir. Ön ek kullanarak kaynak dosyadaki sabit değerler için UTF-8 kodlaması belirtebilirsiniz `u8` . Derleyici bu UTF-8 kodlu dizeleri çıkışa geçirir. U8 kullanılarak önekli dar karakter değişmez değerleri bir bayta sığması veya çıkışta kesilmelidir.

Varsayılan olarak, Visual Studio, çıkış için kaynak kodunuzu yorumlamak için kullanılan kaynak karakter kümesi olarak geçerli kod sayfasını kullanır. Bir dosya okurken, dosya kodu sayfası ayarlanmadığı veya dosyanın başlangıcında bir bayt sırası işareti (BOM) veya UTF-16 karakteri algılanmamışsa, Visual Studio bunu geçerli kod sayfasına göre yorumlar. Windows 'un bazı sürümlerinde UTF-8 ' i geçerli kod sayfası olarak ayarlayamazsınız. Otomatik algılama, bu sürümlerde bir BOM olmadan UTF-8 olarak kodlanmış kaynak dosyalarını bulduğunda, Visual Studio geçerli kod sayfası kullanılarak kodlandığını varsayar. Kaynak dosyadaki, belirtilen veya otomatik olarak algılanan kod sayfasının dışında kalan karakterler derleyici uyarılarına ve hatalara neden olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)\
[`/execution-charset` (Yürütme karakter kümesini Ayarla)](../build/reference/execution-charset-set-execution-character-set.md)\
[`/utf-8` (Kaynak ve yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)
