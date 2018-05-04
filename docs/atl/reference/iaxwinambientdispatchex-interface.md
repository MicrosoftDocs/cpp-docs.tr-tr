---
title: IAxWinAmbientDispatchEx arabirimi | Microsoft Docs
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
ms.openlocfilehash: 22815ddf3131b9d262d68a3202f4f500b7edf807
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="iaxwinambientdispatchex-interface"></a>IAxWinAmbientDispatchEx arabirimi
Bu arabirim barındırılan denetimi için ek ortam özelliklerine uygular.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
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
 ATL ve konak ActiveX denetimleri, özellikle ActiveX ortam özelliklerine sahip denetimleri için statik olarak bağlantılı ATL uygulamalarında bu arabirimi içerir. Bu arabirim hariç bu onaylama üretir: "kimliği için CComModule::Init geçirmek unuttunuz"  
  
 Bu arabirim nesneleri barındırma ATL'in ActiveX denetimi tarafından sunulur. Türetilmiş [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` biriyle kendi ATL tarafından sağlanan ortam özelliği arabirimi desteklemek üzere izin veren bir yöntem ekler.  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) hakkında türü bilgileri yüklenmeye çalışılacak `IAxWinAmbientDispatch` ve `IAxWinAmbientDispatchEx` tür kitaplığından kodunu içerir.  
  
 ATL90.dll için bağlıyorsanız **AXHost** türü bilgileri DLL'deki tür kitaplığından yükler.  
  
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
 Yeni arabirimi işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `SetAmbientDispatch` çağrılır herhangi bir özellik veya için bu özellikleri zaten tarafından sağlanmamışsa barındırılan denetim tarafından sorulan yöntemleri çağırmak için bu yeni arabirim kullanılacak yeni bir arabirimi için bir işaretçi ile [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IAxWinAmbientDispatch Arabirimi](../../atl/reference/iaxwinambientdispatch-interface.md)
