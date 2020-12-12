---
description: 'Hakkında daha fazla bilgi edinin: _com_ptr_t:: CreateInstance'
title: _com_ptr_t::CreateInstance
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::CreateInstance
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
ms.openlocfilehash: dd7ef236f25c22b25c9c083aea8439f5f5175d5b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295529"
---
# <a name="_com_ptr_tcreateinstance"></a>_com_ptr_t::CreateInstance

**Microsoft'a Özgü**

Veya verilen bir nesnenin yeni bir örneğini oluşturur `CLSID` `ProgID` .

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
`CLSID`Bir nesne.

*Clsıdstring*<br/>
`CLSID`("**{**" İle başlayarak) veya içeren bir Unicode dizesi `ProgID` .

*Clsıdstringa*<br/>
`CLSID`("**{**" İle başlayarak) veya ' ı içeren ANSI kod sayfası kullanan çok baytlı bir dize `ProgID` .

*dwClsContext*<br/>
Yürütülebilir kodu çalıştırmak için bağlam.

*pOuter*<br/>
[Toplama](../atl/aggregation.md)için bilinmeyen dış.

## <a name="remarks"></a>Açıklamalar

Bu üye işlevleri `CoCreateInstance` , yeni BIR com nesnesi oluşturmak ve ardından bu akıllı işaretçinin arabirim türüne yönelik sorgular için çağırır. Elde edilen işaretçi, daha bu `_com_ptr_t` nesnesinin içinde kapsüllenir. `Release` , daha önce kapsüllenmiş işaretçinin başvuru sayısını azaltmak için çağırılır. Bu yordam, başarılı veya başarısız olduğunu göstermek için HRESULT döndürür.

- **CreateInstance (**  *rclsıd* **,**  *dwClsContext*  **)** Verilen bir nesnenin yeni bir çalışan örneğini oluşturur `CLSID` .

- **CreateInstance (**  *clsidstring* **,**  *dwClsContext*  **)** `CLSID` ("**{**" İle başlayarak) veya içeren bir Unicode dizesi verilen bir nesne için yeni bir çalışan örneği oluşturur `ProgID` .

- **CreateInstance (**  *clsidstringa* **,**  *dwClsContext*  **)** `CLSID` ("**{**" İle başlayarak) veya ' i tutan çok baytlı bir karakter dizesi verilen bir nesnenin yeni bir çalışan örneğini oluşturur `ProgID` . Dizenin bir OEM kod sayfası yerine ANSI kod sayfasında olduğunu varsayan [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)' ı çağırır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)
