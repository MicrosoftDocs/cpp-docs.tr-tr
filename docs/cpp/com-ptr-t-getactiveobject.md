---
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: ea8059a039b77811dd54d4a4937ad746b7ca0937
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170807"
---
# <a name="_com_ptr_tgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Microsoft 'a özgü**

`CLSID` veya `ProgID`verilen bir nesnenin var olan örneğine iliştirir.

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
Bir nesnenin `CLSID`.

*Clsıdstring*<br/>
Bir `CLSID` (" **{** " ile başlayarak) ya da bir `ProgID`tutan bir Unicode dizesi.

*Clsıdstringa*<br/>
Bir `CLSID` (" **{** " ile başlayarak) veya bir `ProgID`tutan, ANSI kod sayfası kullanan çok baytlı bir dize.

## <a name="remarks"></a>Açıklamalar

Bu üye işlevleri, OLE ile kaydedilmiş çalışan bir nesnenin işaretçisini almak için **GetActiveObject** öğesini çağırır ve ardından bu akıllı işaretçinin arabirim türünü sorgular. Elde edilen işaretçi, daha bu `_com_ptr_t` nesnesinin içinde kapsüllenir. `Release`, daha önce kapsüllenmiş işaretçinin başvuru sayısını azaltmak için çağrılır. Bu yordam, başarılı veya başarısız olduğunu göstermek için HRESULT döndürür.

- **GetActiveObject (** `rclsid` **)** `CLSID`verilen bir nesnenin var olan örneğine iliştirir.

- **GetActiveObject (** `clsidString` **)** Bir `CLSID` ("{" ile başlayarak) veya bir `ProgID`(" **{** " ile başlayarak) tutan bir Unicode dizesi verilen bir nesnenin varolan örneğine iliştirir.

- **GetActiveObject (** `clsidStringA` **)** Bir `CLSID` (" **{** " ile başlayarak) ya da bir `ProgID`tutan çok baytlı bir karakter dizesi verilen bir nesnenin varolan bir örneğine iliştirir. Dizenin bir OEM kod sayfası yerine ANSI kod sayfasında olduğunu varsayan [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)' ı çağırır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)
