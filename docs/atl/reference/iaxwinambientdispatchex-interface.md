---
title: IAxWinAmbientDispatchEx Interface
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
ms.openlocfilehash: ae91921ecd5f53f4551e46e1d03cf027ce3e1f3b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57292414"
---
# <a name="iaxwinambientdispatchex-interface"></a>IAxWinAmbientDispatchEx Interface

Bu arabirim, barındırılan bir denetim için ek ortam özelliklerine uygular.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[SetAmbientDispatch](#setambientdispatch)|Bu yöntem, kullanıcı tanımlı bir arabirimi varsayılan ortam özelliği arabirimiyle desteklemek üzere çağrılır.|

## <a name="remarks"></a>Açıklamalar

Bu arabirimi statik olarak, ATL ve konak ActiveX denetimleri, özellikle ActiveX ortam özelliklerine sahip denetimler için bağlı olan ATL uygulamaları içermektedir. Bu arabirim dahil değil, bu onay oluşturur: "Kitaplık kimliği için Ccommodule::Init geçirilecek unuttunuz"

Bu arabirim, nesneler barındırma ATL'nin ActiveX denetimi tarafından kullanıma sunulur. Türetilmiş [Iaxwinambientdispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` biriyle kendi ATL tarafından sağlanan ortam özelliği arabirimi desteklemek üzere izin veren bir yöntem ekler.

[AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) hakkında tür bilgisi yüklenmeye çalışılacak `IAxWinAmbientDispatch` ve `IAxWinAmbientDispatchEx` tür kitaplığından kodunu içerir.

ATL90.dll için bağlıyorsanız **AXHost** dll tür kitaplığındaki tür bilgilerini yükler.

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) daha fazla ayrıntı için.

## <a name="requirements"></a>Gereksinimler

Bu arabirim tanımı aşağıdaki tabloda gösterildiği gibi formlar, bir süre içinde kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|IDL|atliface.idl|
|Tür kitaplığı|ATL.dll|
|C++|atliface.h (ATLBase.h içinde de dahil)|

##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch

Bu yöntem, kullanıcı tanımlı bir arabirimi varsayılan ortam özelliği arabirimiyle desteklemek üzere çağrılır.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Parametreler

*pDispatch*<br/>
Yeni arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Zaman `SetAmbientDispatch` çağrılır yeni bir arabirim işaretçisi ile tüm özellikler veya yöntemler için bu özellikleri zaten tarafından sağlanmazsa barındırılan denetim tarafından sorulan çağırmak için bu yeni arabirim kullanılacak [Iaxwinambientdispatch](../../atl/reference/iaxwinambientdispatch-interface.md).

## <a name="see-also"></a>Ayrıca bkz.

[IAxWinAmbientDispatch Arabirimi](../../atl/reference/iaxwinambientdispatch-interface.md)
