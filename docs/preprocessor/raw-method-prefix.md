---
title: raw_method_prefix
ms.date: 08/29/2019
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: b1bc536507716e5c117718ec825bf7fe76c84b61
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216151"
---
# <a name="raw_method_prefix"></a>raw_method_prefix

**C++Belirli**

Ad çakışmalarını önlemek için farklı bir ön ek belirtir.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **raw_method_prefix (** "*ön ek*" **)**

### <a name="parameters"></a>Parametreler

*Koy*\
Kullanılacak ön ek.

## <a name="remarks"></a>Açıklamalar

Alt düzey özellikler ve Yöntemler, üst düzey hata işleme üye işlevleri ile ad çakışmalarını önlemek için varsayılan bir **raw_** öneki kullanılarak adlandırılan üye işlevleri tarafından gösterilir.

> [!NOTE]
> **Raw_method_prefix** özniteliğinin etkileri [raw_interfaces_only](raw-interfaces-only.md) özniteliğinin varlığı tarafından değiştirilmez. **Raw_method_prefix** her zaman bir ön ek `raw_interfaces_only` belirtmekten önceliklidir. Her iki öznitelik de aynı `#import` bildirimde kullanılıyorsa, **raw_method_prefix** özniteliği tarafından belirtilen önek kullanılır.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
