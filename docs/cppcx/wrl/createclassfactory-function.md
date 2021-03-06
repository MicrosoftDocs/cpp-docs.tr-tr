---
description: 'Daha fazla bilgi edinin: CreateClassFactory Işlevi'
title: CreateClassFactory İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateClassFactory
helpviewer_keywords:
- CreateClassFactory function
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
ms.openlocfilehash: 99565ee732843f57426f10375ffabc7680ef3c62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273065"
---
# <a name="createclassfactory-function"></a>CreateClassFactory İşlevi

Belirtilen sınıfın örneklerini üreten bir fabrika oluşturur.

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

*bayraklar*<br/>
Bir veya daha fazla [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırma değerinin birleşimi.

*girişte*<br/>
Başlatma *ve parametreli parametre* hakkında bilgi Içeren bir [CreatorMap](creatormap-structure.md) işaretçisi.

*riıd*<br/>
Arabirim KIMLIĞINE başvuru.

*ppFactory*<br/>
Bu işlem başarıyla tamamlanırsa, bir sınıf fabrikası işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="remarks"></a>Açıklamalar

Şablon parametresi *fabrikası* arabirimden türetilmezse bir onaylama hatası yayınlanır `IClassFactory` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL:: sarmalayıcılar::D euçlar ad alanı](microsoft-wrl-wrappers-details-namespace.md)
