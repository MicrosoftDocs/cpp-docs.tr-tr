---
title: is_trivially_copyable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copyable
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
ms.openlocfilehash: 181152bff1d7c2e4f97678b48310f744080822ce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554389"
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
