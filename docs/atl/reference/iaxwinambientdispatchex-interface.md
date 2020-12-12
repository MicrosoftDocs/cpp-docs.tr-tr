---
description: 'Daha fazla bilgi edinin: IAxWinAmbientDispatchEx Interface'
title: IAxWinAmbientDispatchEx arabirimi
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
ms.openlocfilehash: c26ce7fb4f41273a498e3b28e9d6e15d4c89f9ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139730"
---
# <a name="iaxwinambientdispatchex-interface"></a>IAxWinAmbientDispatchEx arabirimi

Bu arabirim barındırılan bir denetim için ek çevresel özellikler uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|-|-|
|[Setambentdispatch](#setambientdispatch)|Bu yöntem, Kullanıcı tanımlı bir arabirimle varsayılan çevresel Özellik arabirimini tamamlamak için çağrılır.|

## <a name="remarks"></a>Açıklamalar

Bu arabirimi ATL ve konak ActiveX denetimlerine statik olarak bağlanmış ATL uygulamalarına, özellikle de çevresel özelliklerine sahip ActiveX denetimlerine dahil edin. Bu arabirimin dahil edilmesi bu onay onayını oluşturacaktır: "LIBıD 'yi CComModule:: Init ' e geçirmeye mi unuttunuz?

Bu arabirim, ATL 'nin ActiveX denetimi barındırma nesneleri tarafından sunulur. [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)öğesinden türeten, `IAxWinAmbientDispatchEx` ATL tarafından sunulan çevresel Özellik arabirimini kendi kendinizinkini kullanarak kullanmanıza izin veren bir yöntem ekler.

<xref:System.Windows.Forms.AxHost>`IAxWinAmbientDispatch`kodu içeren tür kitaplığından ve hakkındaki tür bilgilerini yüklemeye çalışır `IAxWinAmbientDispatchEx` .

ATL90.dll bağlıyorsanız, **AxHost** tür bilgilerini dll 'deki tür kitaplığından yükler.

Daha fazla ayrıntı için bkz. [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) .

## <a name="requirements"></a>Gereksinimler

Bu arabirimin tanımı, aşağıdaki tabloda gösterildiği gibi çeşitli formlarda kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|IDL|atlıyüz. IDL|
|Tür kitaplığı|ATL.dll|
|C++|atlıyüz. h (ATLBase. h 'ye de dahildir)|

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a> IAxWinAmbientDispatchEx:: Setambentdispatch

Bu yöntem, Kullanıcı tanımlı bir arabirimle varsayılan çevresel Özellik arabirimini tamamlamak için çağrılır.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Parametreler

*pDispatch*<br/>
Yeni arabirime yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

`SetAmbientDispatch`Yeni bir arabirim işaretçisi ile çağrıldığında bu yeni arabirim, barındırılan denetim tarafından istenen özellikleri veya yöntemleri çağırmak için kullanılır. bu özellikler zaten [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)tarafından sağlanmamıştır.

## <a name="see-also"></a>Ayrıca bkz.

[IAxWinAmbientDispatch arabirimi](../../atl/reference/iaxwinambientdispatch-interface.md)
