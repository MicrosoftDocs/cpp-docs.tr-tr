---
description: 'Hakkında daha fazla bilgi edinin: raw_method_prefix'
title: raw_method_prefix
ms.date: 08/29/2019
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: 9e05f70814e48a4460287e96905b543f7d76dde6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201995"
---
# <a name="raw_method_prefix"></a>raw_method_prefix

**C++ özel**

Ad çakışmalarını önlemek için farklı bir ön ek belirtir.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **raw_method_prefix (** "*ön ek*" **)**

### <a name="parameters"></a>Parametreler

*Koy*\
Kullanılacak ön ek.

## <a name="remarks"></a>Açıklamalar

Alt düzey özellikler ve Yöntemler, üst düzey hata işleme üye işlevleri ile ad çakışmalarını önlemek için varsayılan bir **raw_** öneki kullanılarak adlandırılan üye işlevleri tarafından gösterilir.

> [!NOTE]
> **Raw_method_prefix** özniteliğinin etkileri [raw_interfaces_only](raw-interfaces-only.md) özniteliğinin varlığı tarafından değiştirilmez. **Raw_method_prefix** her zaman `raw_interfaces_only` bir ön ek belirtmekten önceliklidir. Her iki öznitelik de aynı `#import` bildirimde kullanılıyorsa, **raw_method_prefix** özniteliği tarafından belirtilen önek kullanılır.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
