---
title: execution_character_set pragma
ms.date: 08/29/2019
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
helpviewer_keywords:
- pragma execution_character_set
ms.assetid: 32248cbc-7c92-4dca-8442-230c052b53ad
ms.openlocfilehash: 0c2c812f27634f397af91eace7a41c0e71c1eb99
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218631"
---
# <a name="execution_character_set-pragma"></a>execution_character_set pragma

Dize ve karakter değişmez değerleri için kullanılan yürütme karakter kümesini belirtir. Bu yönerge, `u8` önekiyle işaretlenmiş sabit değerler için gerekli değildir.

## <a name="syntax"></a>Sözdizimi

> **#pragma execution_character_set (** "*target*" **)**

### <a name="parameters"></a>Parametreler

*hedef*\
Hedef yürütme karakter kümesini belirtir. Şu anda desteklenen tek hedef yürütme kümesi "UTF-8" dır.

## <a name="remarks"></a>Açıklamalar

Bu derleyici yönergesi Visual Studio 2015 güncelleştirme 2 ' den itibaren kullanımdan kalkmıştır. Ve genişletilmiş karakterler içeren dize sabit `/execution-charset:utf-8` değerleri `/utf-8` ve dar karakter üzerinde `u8` ön eki kullanarak, veya derleyici seçeneklerini kullanmanızı öneririz. `u8` Ön ek hakkında daha fazla bilgi için bkz. [dize ve karakter sabit değerleri](../cpp/string-and-character-literals-cpp.md). Derleyici seçenekleri hakkında daha fazla bilgi için bkz. [/Execution-charset (yürütme karakter kümesini Ayarla)](../build/reference/execution-charset-set-execution-character-set.md) ve [/UTF-8 belirtildiğinde (kaynak ve yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md).

`#pragma execution_character_set("utf-8")` Yönergesi derleyiciye, kaynak kodunuzda dar karakter ve dar dize sabit değerlerini yürütülebilir dosyada UTF-8 olarak kodlamasını söyler. Bu çıkış kodlaması kullanılan kaynak dosya kodlamasından bağımsızdır.

Varsayılan olarak, derleyici, geçerli kod sayfasını yürütme karakter kümesi olarak kullanarak dar karakterleri ve dar dizeleri kodluyor. Bu, geçerli kod sayfasının dışındaki bir sabit değer içindeki Unicode veya DBCS karakterlerinin çıktıda varsayılan değiştirme karakterine dönüştürüldüğü anlamına gelir. Unicode ve DBCS karakterleri, düşük sıralı baytlarına kesilir. Bu, neredeyse istediğiniz şeydir. `u8` Ön ek kullanarak kaynak dosyadaki sabit değerler için UTF-8 kodlaması belirtebilirsiniz. Derleyici bu UTF-8 kodlu dizeleri çıkışa geçirir. U8 kullanılarak önekli dar karakter değişmez değerleri bir bayta sığması veya çıkışta kesilmelidir.

Varsayılan olarak, Visual Studio, çıkış için kaynak kodunuzu yorumlamak için kullanılan kaynak karakter kümesi olarak geçerli kod sayfasını kullanır. Bir dosya okurken, dosya kodu sayfası ayarlanmadığı veya dosyanın başlangıcında bir bayt sırası işareti (BOM) veya UTF-16 karakteri algılanmamışsa, Visual Studio bunu geçerli kod sayfasına göre yorumlar. UTF-8 geçerli kod olarak ayarlanamadığından, otomatik algılama, bir BOM olmadan UTF-8 olarak kodlanmış kaynak dosyalarla karşılaştığında, Visual Studio geçerli kod sayfası kullanılarak kodlandığını varsayar. Kaynak dosyadaki, belirtilen veya otomatik olarak algılanan kod sayfasının dışında kalan karakterler derleyici uyarılarına ve hatalara neden olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve \_ \_pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[/Execution-charset (yürütme karakter kümesini Ayarla)](../build/reference/execution-charset-set-execution-character-set.md)\
[/utf-8 (Kaynak ve Yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)
