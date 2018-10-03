---
title: DontUseNewUseMake sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::DontUseNewUseMake class
- Microsoft::WRL::Details::DontUseNewUseMake::operator new operator
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c1f3a57401a3ab2efd45cab2dace127010c24e6
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235288"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>Açıklamalar

İşleç engel `new` içinde `RuntimeClass`. Sonuç olarak, kullanmanız gereken [olun işlevi](../windows/make-function.md) yerine.

## <a name="members"></a>Üyeler

### <a name="public-operators"></a>Ortak İşleçler

Ad                                             | Açıklama
------------------------------------------------ | ---------------------------------------------------------------------------
[DontUseNewUseMake::operator yeni](#operator-new) | İşleç aşırı `new` ve içinde kullanılmasını engeller `RuntimeClass`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`DontUseNewUseMake`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="operator-new"></a>DontUseNewUseMake::operator yeni

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>Parametreler

*__unnamed0*<br/>
Bir adlandırılmamış parametresi ayrılacak bellek bayt sayısını belirtir.

*yerleştirme*<br/>
Ayrılacak türü.

### <a name="return-value"></a>Dönüş Değeri

İşleç işlecini aşırı yüklediyseniz ek bağımsız değişkenleri geçirmek için bir yol sağlar `new`.

### <a name="remarks"></a>Açıklamalar

İşleç aşırı `new` ve içinde kullanılmasını engeller `RuntimeClass`.
