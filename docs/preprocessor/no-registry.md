---
description: 'Hakkında daha fazla bilgi edinin: no_registry Import özniteliği'
title: no_registry içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- no_registry
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
ms.openlocfilehash: fa33bf8096a92ec248b0a9d56e39fcc82f433206
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333300"
---
# <a name="no_registry-import-attribute"></a>no_registry içeri aktarma özniteliği

**no_registry** , derleyicisine, ile içeri aktarılan tür kitaplıklarının kayıt defterinde arama olmadığını söyler `#import` .

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **no_registry**

### <a name="parameters"></a>Parametreler

*tür kitaplığı*\
Bir tür kitaplığı.

## <a name="remarks"></a>Açıklamalar

Başvurulan bir tür kitaplığı içerme dizinlerinde bulunmazsa, tür kitaplığı kayıt defterinde olsa bile derleme başarısız olur.  **no_registry** , ile örtülü olarak içeri aktarılan diğer tür kitaplıklarına yayar `auto_search` .

Derleyici, dosya adıyla belirtilen ve doğrudan öğesine geçirilen tür kitaplıkları için kayıt defterini hiçbir şekilde araymayın `#import` .

Belirtildiğinde `auto_search` , ek `#import` yönergeler başlangıçtaki **no_registry** ayarı kullanılarak oluşturulur `#import` . Başlangıç `#import` yönergesi **no_registry** ise, bir `auto_search` `#import` **no_registry** de oluşturulur.

çapraz referanslı tür kitaplıklarını içeri aktarmak istiyorsanız **no_registry** yararlıdır. Derleyicinin kayıt defterindeki dosyanın daha eski bir sürümünü bulmasını önler. **no_registry** , tür kitaplığı kayıtlı değilse da yararlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
