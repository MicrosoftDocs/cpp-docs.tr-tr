---
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: f13a42878392f63096cdfcb405f3f91cc0efe451
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498892"
---
# <a name="_com_ptr_tgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Microsoft 'a özgü**

`CLSID` Veya`ProgID`verilen bir nesnenin var olan örneğine iliştirir.

## <a name="syntax"></a>Sözdizimi

```
HRESULT GetActiveObject(
   const CLSID& rclsid
) throw( );
HRESULT GetActiveObject(
   LPCWSTR clsidString
) throw( );
HRESULT GetActiveObject(
   LPCSTR clsidStringA
) throw( );
```

#### <a name="parameters"></a>Parametreler

*rclsıd*<br/>
`CLSID` Bir nesne.

*Clsıdstring*<br/>
`CLSID` (" **{** `ProgID`" İle başlayarak) veya içeren bir Unicode dizesi.

*Clsıdstringa*<br/>
`CLSID` (" **{** `ProgID`" İle başlayarak) veya ' ı içeren ANSI kod sayfası kullanan çok baytlı bir dize.

## <a name="remarks"></a>Açıklamalar

Bu üye işlevleri, OLE ile kaydedilmiş çalışan bir nesnenin işaretçisini almak için **GetActiveObject** öğesini çağırır ve ardından bu akıllı işaretçinin arabirim türünü sorgular. Elde edilen işaretçi, daha bu `_com_ptr_t` nesnesinin içinde kapsüllenir. `Release`, daha önce kapsüllenmiş işaretçinin başvuru sayısını azaltmak için çağırılır. Bu yordam, başarılı veya başarısız olduğunu göstermek için HRESULT döndürür.

- **GetActiveObject (** `rclsid` **)** , verilen bir `CLSID`nesnenin var olan bir örneğine iliştirir.

- **GetActiveObject (** `clsidString` **)** , `CLSID` (" **{** " ile `ProgID`başlayarak) veya içeren bir Unicode dizesi verilen bir nesnenin varolan bir örneğine iliştirir.

- **GetActiveObject (** `clsidStringA` **)** , `CLSID` (" **{** " ile `ProgID`başlayarak) veya ' i tutan çok baytlı bir karakter dizesi verilen bir nesnenin varolan bir örneğine iliştirir. Dizenin bir OEM kod sayfası yerine ANSI kod sayfasında olduğunu varsayan [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)' ı çağırır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)