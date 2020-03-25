---
title: _com_ptr_t::CreateInstance
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::CreateInstance
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
ms.openlocfilehash: 2ec4e90c8f0c1009cc47e9022a09b3b8f7dbb284
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190007"
---
# <a name="_com_ptr_tcreateinstance"></a>_com_ptr_t::CreateInstance

**Microsoft 'a özgü**

`CLSID` veya `ProgID`verilen bir nesnenin yeni bir örneğini oluşturur.

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
Bir nesnenin `CLSID`.

*Clsıdstring*<br/>
Bir `CLSID` (" **{** " ile başlayarak) ya da bir `ProgID`tutan bir Unicode dizesi.

*Clsıdstringa*<br/>
Bir `CLSID` (" **{** " ile başlayarak) veya bir `ProgID`tutan, ANSI kod sayfası kullanan çok baytlı bir dize.

*dwClsContext*<br/>
Yürütülebilir kodu çalıştırmak için bağlam.

*pOuter*<br/>
[Toplama](../atl/aggregation.md)için bilinmeyen dış.

## <a name="remarks"></a>Açıklamalar

Bu üye işlevleri, yeni bir COM nesnesi oluşturmak için `CoCreateInstance` çağırır ve ardından bu akıllı işaretçinin arabirim türünü sorgular. Elde edilen işaretçi, daha bu `_com_ptr_t` nesnesinin içinde kapsüllenir. `Release`, daha önce kapsüllenmiş işaretçinin başvuru sayısını azaltmak için çağrılır. Bu yordam, başarılı veya başarısız olduğunu göstermek için HRESULT döndürür.

- **CreateInstance (**  *rclsıd* **,**  *dwClsContext*  **)** `CLSID`verilen bir nesnenin yeni bir çalışan örneğini oluşturur.

- **CreateInstance (**  *clsidstring* **,**  *dwClsContext*  **)** Bir `CLSID` (" **{** " ile başlayarak) veya bir `ProgID`tutan bir Unicode dizesi verilen bir nesnenin yeni bir çalışan örneğini oluşturur.

- **CreateInstance (**  *clsidstringa* **,**  *dwClsContext*  **)** Bir `CLSID` (" **{** " ile başlayarak) ya da bir `ProgID`tutan çok baytlı bir karakter dizesi verilen yeni bir çalışan örneği oluşturur. Dizenin bir OEM kod sayfası yerine ANSI kod sayfasında olduğunu varsayan [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)' ı çağırır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)
