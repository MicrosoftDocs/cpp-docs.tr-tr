---
description: 'Daha fazla bilgi edinin: execution_character_set pragma'
title: execution_character_set pragma
ms.date: 08/29/2019
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
helpviewer_keywords:
- pragma execution_character_set
ms.assetid: 32248cbc-7c92-4dca-8442-230c052b53ad
ms.openlocfilehash: 057013e669d7c6a4b31c02fe9c6319ea05eb7780
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300495"
---
# <a name="execution_character_set-pragma"></a>execution_character_set pragma

Dize ve karakter değişmez değerleri için kullanılan yürütme karakter kümesini belirtir. Bu yönerge, önekiyle işaretlenmiş sabit değerler için gerekli değildir `u8` .

## <a name="syntax"></a>Syntax

> **#pragma execution_character_set (** "*target*" **)**

### <a name="parameters"></a>Parametreler

*hedef*\
Hedef yürütme karakter kümesini belirtir. Şu anda desteklenen tek hedef yürütme kümesi "UTF-8" dır.

## <a name="remarks"></a>Açıklamalar

Bu derleyici yönergesi Visual Studio 2015 güncelleştirme 2 ' den itibaren kullanımdan kalkmıştır. Ve `/execution-charset:utf-8` `/utf-8` `u8` genişletilmiş karakterler içeren dize sabit değerleri ve dar karakter üzerinde ön eki kullanarak, veya derleyici seçeneklerini kullanmanızı öneririz. Ön ek hakkında daha fazla bilgi için `u8` bkz. [dize ve karakter sabit değerleri](../cpp/string-and-character-literals-cpp.md). Derleyici seçenekleri hakkında daha fazla bilgi için bkz. [/Execution-charset (yürütme karakter kümesini Ayarla)](../build/reference/execution-charset-set-execution-character-set.md) ve [/UTF-8 belirtildiğinde (kaynak ve yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md).

`#pragma execution_character_set("utf-8")`Yönergesi derleyiciye, kaynak kodunuzda dar karakter ve dar dize sabit değerlerini yürütülebilir dosyada UTF-8 olarak kodlamasını söyler. Bu çıkış kodlaması kullanılan kaynak dosya kodlamasından bağımsızdır.

Varsayılan olarak, derleyici, geçerli kod sayfasını yürütme karakter kümesi olarak kullanarak dar karakterleri ve dar dizeleri kodluyor. Bu, geçerli kod sayfasının dışındaki bir sabit değer içindeki Unicode veya DBCS karakterlerinin çıktıda varsayılan değiştirme karakterine dönüştürüldüğü anlamına gelir. Unicode ve DBCS karakterleri, düşük sıralı baytlarına kesilir. Bu, neredeyse istediğiniz şeydir. Ön ek kullanarak kaynak dosyadaki sabit değerler için UTF-8 kodlaması belirtebilirsiniz `u8` . Derleyici bu UTF-8 kodlu dizeleri çıkışa geçirir. U8 kullanılarak önekli dar karakter değişmez değerleri bir bayta sığması veya çıkışta kesilmelidir.

Varsayılan olarak, Visual Studio, çıkış için kaynak kodunuzu yorumlamak için kullanılan kaynak karakter kümesi olarak geçerli kod sayfasını kullanır. Bir dosya okurken, dosya kodu sayfası ayarlanmadığı veya dosyanın başlangıcında bir bayt sırası işareti (BOM) veya UTF-16 karakteri algılanmamışsa, Visual Studio bunu geçerli kod sayfasına göre yorumlar. UTF-8 geçerli kod olarak ayarlanamadığından, otomatik algılama, bir BOM olmadan UTF-8 olarak kodlanmış kaynak dosyalarla karşılaştığında, Visual Studio geçerli kod sayfası kullanılarak kodlandığını varsayar. Kaynak dosyadaki, belirtilen veya otomatik olarak algılanan kod sayfasının dışında kalan karakterler derleyici uyarılarına ve hatalara neden olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve \_ \_ pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[/Execution-charset (yürütme karakter kümesini Ayarla)](../build/reference/execution-charset-set-execution-character-set.md)\
[/UTF-8 belirtildiğinde (kaynak ve yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)
