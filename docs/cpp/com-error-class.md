---
title: "_com_error sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error
dev_langs: C++
helpviewer_keywords: _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 47ee4686c5c0a239b868d6da9aaccc332def19dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comerror-class"></a>_com_error Sınıfı
**Microsoft özel**  
  
 A `_com_error` nesne türü Kitaplığı'ndan oluşturulan üstbilgi dosyalarında hata işleme sarmalayıcı işlevleri veya COM desteği sınıfları biri tarafından algılanan bir özel durumu temsil eder. `_com_error` Sınıfı yalıtır `HRESULT` hata kodu ve varsa ilişkili `IErrorInfo Interface` nesnesi.  
  
### <a name="construction"></a>Yapı  
  
|||  
|-|-|  
|[_com_error](../cpp/com-error-com-error.md)|Oluşturan bir `_com_error` nesnesi.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](../cpp/com-error-operator-equal.md)|Var olan atar `_com_error` başka bir nesne.|  
  
### <a name="extractor-functions"></a>Ayıklayıcısı işlevleri  
  
|||  
|-|-|  
|[Hata](../cpp/com-error-error.md)|Alır `HRESULT` oluşturucuya geçirilen.|  
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Alır `IErrorInfo` oluşturucuya nesnesi geçirildi.|  
|[WCode](../cpp/com-error-wcode.md)|Kapsüllenmiş eşlenen 16 bit hata kodu alır `HRESULT`.|  
  
### <a name="ierrorinfo-functions"></a>IErrorInfo işlevleri  
  
|||  
|-|-|  
|[Açıklama](../cpp/com-error-description.md)|Çağrıları `IErrorInfo::GetDescription` işlevi.|  
|[HelpContext](../cpp/com-error-helpcontext.md)|Çağrıları `IErrorInfo::GetHelpContext` işlevi.|  
|[HelpFile](../cpp/com-error-helpfile.md)|Çağrıları `IErrorInfo::GetHelpFile` işlevi|  
|[Kaynak](../cpp/com-error-source.md)|Çağrıları `IErrorInfo::GetSource` işlevi.|  
|[GUID](../cpp/com-error-guid.md)|Çağrıları `IErrorInfo::GetGUID` işlevi.|  
  
### <a name="format-message-extractor"></a>Biçim ileti ayıklayıcısı  
  
|||  
|-|-|  
|[ErrorMessage](../cpp/com-error-errormessage.md)|HRESULT depolanan dize ileti alır `_com_error` nesnesi.|  
  
### <a name="exepinfowcode-to-hresult-mappers"></a>HRESULT Mappers ExepInfo.wCode  
  
|||  
|-|-|  
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|32-bit eşlemeleri `HRESULT` için 16 bit `wCode`.|  
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|16 bit `wCode`'u 32 bit `HRESULT` ile eşleştirir.|  
  
**SON Microsoft özel**  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** comdef.h  
  
 `Lib:`comsuppw.lib veya comsuppwd.lib (bkz [/ZC: wchar_t (wchar_t yerel tür olan)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) daha fazla bilgi için)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici COM desteği sınıfları](../cpp/compiler-com-support-classes.md)   
 [IErrorInfo arabirimi](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)