---
title: CreateClassFactory İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateClassFactory
helpviewer_keywords:
- CreateClassFactory function
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
ms.openlocfilehash: e7e213d1b0679f17ce070de85ee9410ff9546716
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335234"
---
# <a name="createclassfactory-function"></a>CreateClassFactory İşlevi

Belirtilen sınıfın örneklerini oluşturan bir Üreteç oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Factory>
inline HRESULT STDMETHODCALLTYPE CreateClassFactory(
   _In_ unsigned int *flags,
   _In_ const CreatorMap* entry,
   REFIID riid,
   _Outptr_ IUnknown **ppFactory
) throw();
```

### <a name="parameters"></a>Parametreler

*bayrakları*<br/>
Bir veya daha fazla birleşimi [RuntimeClassType](runtimeclasstype-enumeration.md) sabit listesi değerleri.

*entry*<br/>
İşaretçi bir [CreatorMap](creatormap-structure.md) parametresi başlatma ve kayıt bilgilerini içeren *riid*.

*riid*<br/>
Başvuru için bir arabirim kimliği.

*ppFactory*<br/>
Bu işlem bir sınıf üreteci için bir işaretçi başarıyla tamamlanırsa.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="remarks"></a>Açıklamalar

Assert hata durumunda yayıldığını şablon parametresi *Fabrika* arabiriminden türetilen değil `IClassFactory`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers::Details Ad Alanı](microsoft-wrl-wrappers-details-namespace.md)