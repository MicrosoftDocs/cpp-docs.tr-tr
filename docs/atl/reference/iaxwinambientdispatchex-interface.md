---
title: IAxWinAmbientDispatchEx Arabirimi
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
ms.openlocfilehash: f4816846801e388619db62998ec979a1100916ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329988"
---
# <a name="iaxwinambientdispatchex-interface"></a>IAxWinAmbientDispatchEx Arabirimi

Bu arabirim, barındırılan denetim için ek ortam özellikleri uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[SetAmbientDispatch](#setambientdispatch)|Bu yöntem, varsayılan ortam özelliği arabirimini kullanıcı tanımlı bir arabirimle tamamlamak için çağrılır.|

## <a name="remarks"></a>Açıklamalar

Bu arabirimi, statik olarak ATL'ye bağlı ATL uygulamalarına ekleyin ve ActiveX Denetimlerini, özellikle ortam özelliklerine sahip ActiveX Denetimlerini barındırın. Bu arayüz dahil değil bu iddia yı oluşturacaktır: "Libid'i CComModule'e geçirmeyi unuttunuz mu:Init"

Bu arabirim, ATL'nin ActiveX denetim barındırma nesneleri tarafından ortaya çıkarır. [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)türetilmiştir , `IAxWinAmbientDispatchEx` kendi biri ile ATL tarafından sağlanan ortam özelliği arayüzü tamamlamak için izin veren bir yöntem ekler.

<xref:System.Windows.Forms.AxHost>kodu içeren tür kitaplığı hakkında `IAxWinAmbientDispatch` ve `IAxWinAmbientDispatchEx` bu tür kitaplığından tür bilgilerini yüklemeye çalışır.

ATL90.dll'ye bağlayacaksanız, **AXHost** dll'deki tür kitaplığından tür bilgilerini yükler.

Daha fazla bilgi için [ATL AXHost kullanarak ActiveX Denetimleri Barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bakın.

## <a name="requirements"></a>Gereksinimler

Bu arabirimin tanımı, aşağıdaki tabloda gösterildiği gibi, çeşitli formlarda kullanılabilir.

|Tanım Türü|Dosya|
|---------------------|----------|
|ıdl|atliface.idl|
|Tür Kitaplığı|ATL.dll|
|C++|atliface.h (Ayrıca ATLBase.h dahil)|

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a>IAxWinAmbientDispatchEx::SetAmbientDispatch

Bu yöntem, varsayılan ortam özelliği arabirimini kullanıcı tanımlı bir arabirimle tamamlamak için çağrılır.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Parametreler

*pDispatch*<br/>
Yeni arabirimi işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Yeni `SetAmbientDispatch` bir arabirim için bir işaretçi ile çağrıldığında, bu yeni arabirim barındırılan denetim tarafından istenen herhangi bir özellik veya yöntemleri çağırmak için kullanılacak, bu özellikleri zaten [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)tarafından sağlanmadı.

## <a name="see-also"></a>Ayrıca bkz.

[IAxWinAmbientDispatch Arabirimi](../../atl/reference/iaxwinambientdispatch-interface.md)
