---
title: CreateActivationFactory İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
ms.openlocfilehash: ab03b15a968c6aba3fa6df8c975fb98e873f8e23
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214077"
---
# <a name="createactivationfactory-function"></a>CreateActivationFactory İşlevi

Windows Çalışma Zamanı tarafından etkinleştirilenebilir belirtilen sınıfın örneklerini üreten bir fabrika oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Factory>
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,
      REFIID riid,
   _Outptr_ IUnknown **ppFactory) throw();
```

### <a name="parameters"></a>Parametreler

*larına*<br/>
Bir veya daha fazla [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırma değerinin birleşimi.

*entry*<br/>
Başlatma *ve parametreli parametre*hakkında bilgi Içeren bir [CreatorMap](creatormap-structure.md) işaretçisi.

*riıd*<br/>
Arabirim KIMLIĞINE başvuru.

*ppFactory*<br/>
Bu işlem başarıyla tamamlanırsa, bir etkinleştirme fabrikası işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="remarks"></a>Açıklamalar

Şablon parametre *fabrikası* `IActivationFactory`arabiriminden türetilmezse bir onaylama hatası yayınlanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Wrappers::Details Ad Alanı](microsoft-wrl-wrappers-details-namespace.md)
