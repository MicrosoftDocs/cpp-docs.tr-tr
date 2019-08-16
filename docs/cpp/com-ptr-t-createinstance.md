---
title: _com_ptr_t::CreateInstance
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::CreateInstance
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
ms.openlocfilehash: 82b180b3f40683495ed2cfa284bdae8e1afaef9e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498657"
---
# <a name="_com_ptr_tcreateinstance"></a>_com_ptr_t::CreateInstance

**Microsoft 'a özgü**

`CLSID` Veya`ProgID`verilen bir nesnenin yeni bir örneğini oluşturur.

## <a name="syntax"></a>Sözdizimi

```
HRESULT CreateInstance(
   const CLSID& rclsid,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCWSTR clsidString,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCSTR clsidStringA,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
```

#### <a name="parameters"></a>Parametreler

*rclsıd*<br/>
`CLSID` Bir nesne.

*Clsıdstring*<br/>
`CLSID` (" **{** `ProgID`" İle başlayarak) veya içeren bir Unicode dizesi.

*Clsıdstringa*<br/>
`CLSID` (" **{** `ProgID`" İle başlayarak) veya ' ı içeren ANSI kod sayfası kullanan çok baytlı bir dize.

*dwClsContext*<br/>
Yürütülebilir kodu çalıştırmak için bağlam.

*pOuter*<br/>
[Toplama](../atl/aggregation.md)için bilinmeyen dış.

## <a name="remarks"></a>Açıklamalar

Bu üye işlevleri, `CoCreateInstance` yeni bir com nesnesi oluşturmak ve ardından bu akıllı işaretçinin arabirim türüne yönelik sorgular için çağırır. Elde edilen işaretçi, daha bu `_com_ptr_t` nesnesinin içinde kapsüllenir. `Release`, daha önce kapsüllenmiş işaretçinin başvuru sayısını azaltmak için çağırılır. Bu yordam, başarılı veya başarısız olduğunu göstermek için HRESULT döndürür.

- **CreateInstance (** *rclsıd* **,** *dwClsContext* **)** Verilen bir `CLSID`nesnenin yeni bir çalışan örneğini oluşturur.

- **CreateInstance (** *clsidstring* **,** *dwClsContext* **)** `CLSID` (" **{** `ProgID`" İle başlayarak) veya içeren bir Unicode dizesi verilen bir nesne için yeni bir çalışan örneği oluşturur.

- **CreateInstance (** *clsidstringa* **,** *dwClsContext* **)** `CLSID` (" **{** `ProgID`" İle başlayarak) veya ' i tutan çok baytlı bir karakter dizesi verilen bir nesnenin yeni bir çalışan örneğini oluşturur. Dizenin bir OEM kod sayfası yerine ANSI kod sayfasında olduğunu varsayan [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)' ı çağırır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)