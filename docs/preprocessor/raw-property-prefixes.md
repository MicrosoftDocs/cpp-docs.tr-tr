---
title: raw_property_prefixes içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- raw_property_prefixes
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
ms.openlocfilehash: d4d91470781e7c5f673fd228c24904322d1db8b3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216043"
---
# <a name="raw_property_prefixes-import-attribute"></a>raw_property_prefixes içeri aktarma özniteliği

**C++Belirli**

Diğer özellik yöntemi için alternatif önekler belirtir.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **raw_property_prefixes (** "*getprefix*" **,** "*putprefıx*" **,** "*putrefprefix*" **)**

### <a name="parameters"></a>Parametreler

*GetPrefix*\
`propget` Yöntemler için kullanılacak önek.

*PutPrefix*\
`propput` Yöntemler için kullanılacak önek.

*PutRefPrefix*\
`propputref` Yöntemler için kullanılacak önek.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, alt düzey `propget`, `propput`ve `propputref` yöntemleri sırasıyla, `put_`, ve `putref_`' nin `get_`ön eklerini kullanarak adlandırılan üye işlevleri tarafından gösterilir. Bu önekler, MIDL tarafından oluşturulan üstbilgi dosyalarında kullanılan adlarla uyumludur.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
