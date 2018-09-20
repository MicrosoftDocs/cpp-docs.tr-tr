---
title: ComPtr::As yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::As
dev_langs:
- C++
helpviewer_keywords:
- As method
ms.assetid: 2ad6c262-9bdb-4c59-a330-1af8bcd445cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 33f81412ef9580768269663aa23afe06ad4d62f7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374689"
---
# <a name="comptras-method"></a>ComPtr::As Yöntemi

Döndürür bir **ComPtr** belirtilen şablon parametresi tarafından belirlenen arabirimi temsil eden nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* p
) const;

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> p
) const;
```

### <a name="parameters"></a>Parametreler

*U*<br/>
Parametresi tarafından temsil edilmesini arabirimi *p*.

*p*<br/>
A **ComPtr** parametresi tarafından belirtilen arabirim temsil eden nesne *U*. Parametre *p* geçerli entityset'e başvurmadığından **ComPtr** nesne.

## <a name="remarks"></a>Açıklamalar

İlk şablon kodunuzda kullanması gereken biçimidir. İkinci şablonu olduğu gibi C++ dil özellikleri destekleyen bir iç, Yardımcısı özelleştirmesi [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü yazın.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtr Sınıfı](../windows/comptr-class.md)