---
description: 'Hakkında daha fazla bilgi edinin: raw_property_prefixes Import özniteliği'
title: raw_property_prefixes içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- raw_property_prefixes
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
ms.openlocfilehash: 7289f9aeba249249ecf78ffb3ad3b32669ac9fe3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142720"
---
# <a name="raw_property_prefixes-import-attribute"></a>raw_property_prefixes içeri aktarma özniteliği

**C++ özel**

Diğer özellik yöntemi için alternatif önekler belirtir.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **raw_property_prefixes (** "*getprefix*" **,** "*putprefıx*" **,** "*putrefprefix*" **)**

### <a name="parameters"></a>Parametreler

*GetPrefix*\
Yöntemler için kullanılacak önek `propget` .

*PutPrefix*\
Yöntemler için kullanılacak önek `propput` .

*PutRefPrefix*\
Yöntemler için kullanılacak önek `propputref` .

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, alt düzey `propget` , `propput` ve `propputref` yöntemleri sırasıyla,, ve ' nin ön eklerini kullanarak adlandırılan üye işlevleri tarafından gösterilir `get_` `put_` `putref_` . Bu önekler, MIDL tarafından oluşturulan üstbilgi dosyalarında kullanılan adlarla uyumludur.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
