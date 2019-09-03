---
title: no_registry içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- no_registry
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
ms.openlocfilehash: 7c81cc2f570cb9ac4e977dac6d55cb69e491d3b2
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220716"
---
# <a name="no_registry-import-attribute"></a>no_registry içeri aktarma özniteliği

**no_registry** , derleyiciye ile `#import`içeri aktarılan tür kitaplıklarının kayıt defterinde arama olmadığını söyler.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **no_registry**

### <a name="parameters"></a>Parametreler

*tür kitaplığı*\
Bir tür kitaplığı.

## <a name="remarks"></a>Açıklamalar

Başvurulan bir tür kitaplığı içerme dizinlerinde bulunmazsa, tür kitaplığı kayıt defterinde olsa bile derleme başarısız olur.  **no_registry** , ile `auto_search`örtülü olarak içeri aktarılan diğer tür kitaplıklarına yayar.

Derleyici, dosya adıyla belirtilen ve doğrudan öğesine `#import`geçirilen tür kitaplıkları için kayıt defterini hiçbir şekilde araymayın.

Belirtildiğinde, ek `#import` yönergeler başlangıçtaki `#import`no_registry ayarı kullanılarak oluşturulur. `auto_search` Başlangıç `#import` yönergesi **no_registry**ise, a tarafından oluşturulan `auto_search` `#import` bir da **no_registry**.

çapraz referanslı tür kitaplıklarını içeri aktarmak istiyorsanız **no_registry** yararlıdır. Derleyicinin kayıt defterindeki dosyanın daha eski bir sürümünü bulmasını önler. tür kitaplığının kaydı yoksa **no_registry** de yararlı olur.

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
