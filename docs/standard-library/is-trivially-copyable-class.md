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
ms.openlocfilehash: 1577f067b398a53ab4f91847f890beaa96f0639f
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102817"
---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable sınıfı

Türü artık önemsiz olarak kopyalanabilir türü olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* tuttuğu yanlış bir artık önemsiz olarak kopyalanabilir, aksi takdirde türüdür. Artık önemsiz olarak kopyalanabilir türler hiçbir Önemsiz kopyalama işlemleri, taşıma işlemlerini veya yıkıcıları sahip. Genellikle, bir kopyalama işlemi bit düzeyinde bir kopya olarak uygulanması durumunda önemsiz olarak kabul edilir. Yerleşik türler ve önemsiz olarak kopyalanabilir türler, dizileri hem artık önemsiz olarak kopyalanabilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
