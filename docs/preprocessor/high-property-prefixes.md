---
description: 'Hakkında daha fazla bilgi edinin: high_property_prefixes Import özniteliği'
title: high_property_prefixes içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: af6835f5835c23dceadbb5152e36b0dabcbb8c98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167480"
---
# <a name="high_property_prefixes-import-attribute"></a>high_property_prefixes içeri aktarma özniteliği

**C++ özel**

Diğer özellik yöntemi için alternatif önekler belirtir.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **high_property_prefixes (** "*getprefix*" **,** "*putprefıx*" **,** "*putrefprefix*" **)**

### <a name="parameters"></a>Parametreler

*GetPrefix*\
Yöntemler için kullanılacak önek `propget` .

*PutPrefix*\
Yöntemler için kullanılacak önek `propput` .

*PutRefPrefix*\
Yöntemler için kullanılacak önek `propputref` .

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, üst düzey hata işleme `propget` , `propput` ve `propputref` yöntemleri sırasıyla ön ekler `Get` , `Put` , ve olarak adlandırılan üye işlevleri tarafından gösterilir `PutRef` .

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
