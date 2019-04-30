---
title: CreateActivationFactory İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
ms.openlocfilehash: ca3469128cf3d412138d5d39a1587cbc20150699
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398634"
---
# <a name="createactivationfactory-function"></a>CreateActivationFactory İşlevi

Windows çalışma zamanı tarafından etkinleştirilebilen belirtilen sınıf örneklerini oluşturan bir Üreteç oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Factory>
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,
      REFIID riid,
   _Outptr_ IUnknown **ppFactory) throw();
```

### <a name="parameters"></a>Parametreler

*bayrakları*<br/>
Bir veya daha fazla birleşimi [RuntimeClassType](runtimeclasstype-enumeration.md) sabit listesi değerleri.

*entry*<br/>
İşaretçi bir [CreatorMap](creatormap-structure.md) parametresi başlatma ve kayıt bilgilerini içeren *riid*.

*riid*<br/>
Başvuru için bir arabirim kimliği.

*ppFactory*<br/>
Bu işlem bir etkinleştirme fabrikası için bir işaretçi başarıyla tamamlanırsa.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="remarks"></a>Açıklamalar

Assert hata durumunda yayıldığını şablon parametresi *Fabrika* arabiriminden türetilen değil `IActivationFactory`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Wrappers::Details Ad Alanı](microsoft-wrl-wrappers-details-namespace.md)