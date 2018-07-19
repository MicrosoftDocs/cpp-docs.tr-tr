---
title: is_trivially_copyable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copyable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19bed4a455ea2b0b894ba842f349aa304e9f261d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964689"
---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable sınıfı

Türü artık önemsiz olarak kopyalanabilir türü olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>Parametreler

*T* Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* tuttuğu yanlış bir artık önemsiz olarak kopyalanabilir, aksi takdirde türüdür. Artık önemsiz olarak kopyalanabilir türler hiçbir Önemsiz kopyalama işlemleri, taşıma işlemlerini veya yıkıcıları sahip. Genellikle, bir kopyalama işlemi bit düzeyinde bir kopya olarak uygulanması durumunda önemsiz olarak kabul edilir. Yerleşik türler ve önemsiz olarak kopyalanabilir türler, dizileri hem artık önemsiz olarak kopyalanabilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
