---
description: 'Hakkında daha fazla bilgi edinin: _com_ptr_t:: GetActiveObject'
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: 96784e73d91d7be4b0674e09278183fc62e60af2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295477"
---
# <a name="_com_ptr_tgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Microsoft'a Özgü**

Veya verilen bir nesnenin var olan örneğine iliştirir `CLSID` `ProgID` .

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
`CLSID`Bir nesne.

*Clsıdstring*<br/>
`CLSID`("**{**" İle başlayarak) veya içeren bir Unicode dizesi `ProgID` .

*Clsıdstringa*<br/>
`CLSID`("**{**" İle başlayarak) veya ' ı içeren ANSI kod sayfası kullanan çok baytlı bir dize `ProgID` .

## <a name="remarks"></a>Açıklamalar

Bu üye işlevleri, OLE ile kaydedilmiş çalışan bir nesnenin işaretçisini almak için **GetActiveObject** öğesini çağırır ve ardından bu akıllı işaretçinin arabirim türünü sorgular. Elde edilen işaretçi, daha bu `_com_ptr_t` nesnesinin içinde kapsüllenir. `Release` , daha önce kapsüllenmiş işaretçinin başvuru sayısını azaltmak için çağırılır. Bu yordam, başarılı veya başarısız olduğunu göstermek için HRESULT döndürür.

- **GetActiveObject (** `rclsid` **)** , verilen bir nesnenin var olan bir örneğine iliştirir `CLSID` .    

- **GetActiveObject (** `clsidString` **)** , `CLSID` ("**{**" ile başlayarak) veya içeren bir Unicode dizesi verilen bir nesnenin varolan bir örneğine iliştirir `ProgID` .    

- **GetActiveObject (** `clsidStringA` **)** , `CLSID` ("**{**" ile başlayarak) veya ' i tutan çok baytlı bir karakter dizesi verilen bir nesnenin varolan bir örneğine iliştirir `ProgID` .     Dizenin bir OEM kod sayfası yerine ANSI kod sayfasında olduğunu varsayan [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)' ı çağırır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)
