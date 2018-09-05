---
title: Iaxwinambientdispatchex arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
dev_langs:
- C++
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c1c6ed120705886c1b0bb4836e851139543f629
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753918"
---
# <a name="iaxwinambientdispatchex-interface"></a>Iaxwinambientdispatchex arabirimi

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

Bu arabirimi statik olarak, ATL ve konak ActiveX denetimleri, özellikle ActiveX ortam özelliklerine sahip denetimler için bağlı olan ATL uygulamaları içermektedir. Bu arabirim içermeden assertion oluşturacağını: "için Ccommodule::Init LIBID geçirilecek unuttunuz"

Bu arabirim, nesneler barındırma ATL'nin ActiveX denetimi tarafından kullanıma sunulur. Türetilmiş [Iaxwinambientdispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` biriyle kendi ATL tarafından sağlanan ortam özelliği arabirimi desteklemek üzere izin veren bir yöntem ekler.

[AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) hakkında tür bilgisi yüklenmeye çalışılacak `IAxWinAmbientDispatch` ve `IAxWinAmbientDispatchEx` tür kitaplığından kodunu içerir.

ATL90.dll için bağlıyorsanız **AXHost** dll tür kitaplığındaki tür bilgilerini yükler.

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) daha fazla ayrıntı için.

## <a name="requirements"></a>Gereksinimler

Bu arabirim tanımı aşağıdaki tabloda gösterildiği gibi formlar, bir süre içinde kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|IDL|atliface.idl|
|Tür kitaplığı|ATL.|
|C++|atliface.h (ATLBase.h içinde de dahil)|

##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch

Bu yöntem, kullanıcı tanımlı bir arabirimi varsayılan ortam özelliği arabirimiyle desteklemek üzere çağrılır.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Parametreler

*pDispatch*  
Yeni arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Zaman `SetAmbientDispatch` çağrılır yeni bir arabirim işaretçisi ile tüm özellikler veya yöntemler için bu özellikleri zaten tarafından sağlanmazsa barındırılan denetim tarafından sorulan çağırmak için bu yeni arabirim kullanılacak [Iaxwinambientdispatch](../../atl/reference/iaxwinambientdispatch-interface.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IAxWinAmbientDispatch Arabirimi](../../atl/reference/iaxwinambientdispatch-interface.md)
