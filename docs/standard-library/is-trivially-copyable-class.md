---
title: is_trivially_copyable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_trivially_copyable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2e2792c93b477c6d6aac4350045a506eda206eb
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable sınıfı

Türü trivially copyable türü olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>Parametreler

`T` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `T` false tuttuğu trivially copyable, aksi takdirde türüdür. Trivially copyable türleri hiçbir Önemsiz olmayan kopyalama işlemleri, taşıma işlemler veya Yıkıcılar sahip. Genellikle, bir kopyalama işlemi Bitsel kopya olarak uygulanırsa, önemsiz kabul edilir. Yerleşik türler ve diziler trivially copyable türlerinin trivially copyable.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
