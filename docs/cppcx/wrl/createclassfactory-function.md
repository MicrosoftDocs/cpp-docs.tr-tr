---
title: CreateClassFactory İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateClassFactory
helpviewer_keywords:
- CreateClassFactory function
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
ms.openlocfilehash: 0467a9a1341e29a61a3b32d999769b01385f641f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214064"
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

*larına*<br/>
Bir veya daha fazla [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırma değerinin birleşimi.

*entry*<br/>
Başlatma *ve parametreli parametre*hakkında bilgi Içeren bir [CreatorMap](creatormap-structure.md) işaretçisi.

*riıd*<br/>
Arabirim KIMLIĞINE başvuru.

*ppFactory*<br/>
Bu işlem başarıyla tamamlanırsa, bir sınıf fabrikası işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="remarks"></a>Açıklamalar

Şablon parametre *fabrikası* `IClassFactory`arabiriminden türetilmezse bir onaylama hatası yayınlanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Wrappers::Details Ad Alanı](microsoft-wrl-wrappers-details-namespace.md)
