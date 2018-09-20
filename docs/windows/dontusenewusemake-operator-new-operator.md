---
title: DontUseNewUseMake::operator new işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
dev_langs:
- C++
helpviewer_keywords:
- operator new operator
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99e82de06f64816521c47c78648108a9ae815279
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443234"
---
# <a name="dontusenewusemakeoperator-new-operator"></a>DontUseNewUseMake::operator new İşleci

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

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

## <a name="return-value"></a>Dönüş Değeri

İşleç işlecini aşırı yüklediyseniz ek bağımsız değişkenleri geçirmek için bir yol sağlar **yeni**.

## <a name="remarks"></a>Açıklamalar

İşleç aşırı **yeni** ve içinde kullanılmasını engeller `RuntimeClass`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[DontUseNewUseMake Sınıfı](../windows/dontusenewusemake-class.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)