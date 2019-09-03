---
title: high_property_prefixes içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: 9e44f6f1afae479f803f4c6d866ef3ee38744561
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219007"
---
# <a name="high_property_prefixes-import-attribute"></a>high_property_prefixes içeri aktarma özniteliği

**C++Belirli**

Diğer özellik yöntemi için alternatif önekler belirtir.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **high_property_prefixes (** "*getprefix*" **,** "*putprefıx*" **,** "*putrefprefix*" **)**

### <a name="parameters"></a>Parametreler

*GetPrefix*\
`propget` Yöntemler için kullanılacak önek.

*PutPrefix*\
`propput` Yöntemler için kullanılacak önek.

*PutRefPrefix*\
`propputref` Yöntemler için kullanılacak önek.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, üst düzey hata işleme `propget`, `propput`ve `propputref` yöntemleri sırasıyla ön ekler `Get`, `Put`, ve `PutRef`olarak adlandırılan üye işlevleri tarafından gösterilir.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
