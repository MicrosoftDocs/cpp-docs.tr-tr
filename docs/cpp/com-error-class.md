---
title: _com_error sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08ba95eb0e1ffb619b6cdecfc8b410ff5a4b5534
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2018
ms.locfileid: "42465294"
---
# <a name="comerror-class"></a>_com_error Sınıfı
**Microsoft'a özgü**  
  
 A **_com_error** nesnesi, tür kitaplığından oluşturulan üstbilgi dosyalarında hata işleme sarmalayıcı işlevleri veya bir COM desteği sınıfları tarafından algılanan bir özel durum koşulunu temsil eder. **_Com_error** sınıfı Kapsüller HRESULT hata kodu ve varsa ilişkili `IErrorInfo Interface` nesne.  
  
### <a name="construction"></a>Oluşturma  
  
|||  
|-|-|  
|[_com_error](../cpp/com-error-com-error.md)|Oluşturur bir **_com_error** nesne.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](../cpp/com-error-operator-equal.md)|Mevcut bir atar **_com_error** başka bir nesne.|  
  
### <a name="extractor-functions"></a>Ayıklayıcısı işlevleri  
  
|||  
|-|-|  
|[Hata](../cpp/com-error-error.md)|Oluşturucuya geçirilen HRESULT alır.|  
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Alır `IErrorInfo` oluşturucuya nesnesi geçirildi.|  
|[WCode](../cpp/com-error-wcode.md)|Kapsüllenmiş HRESULT biçimine eşlenen 16-bit hata kodunu alır.|  
  
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
|[ErrorMessage](../cpp/com-error-errormessage.md)|HRESULT içinde depolanan için dize iletiyi alır **_com_error** nesne.|  
  
### <a name="exepinfowcode-to-hresult-mappers"></a>HRESULT Azaltıcının için ExepInfo.wCode  
  
|||  
|-|-|  
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|16 bit için 32 bitlik HRESULT eşler `wCode`.|  
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|16-bit eşler `wCode` 32 bitlik HRESULT için.|  
  
**END Microsoft özgü**  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<comdef.h >  
  
 `Lib:` comsuppw.lib veya comsuppwd.lib (bkz [/ZC: wchar_t (wchar_t yerel türü olduğu)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) daha fazla bilgi için)  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Derleyici COM desteği sınıfları](../cpp/compiler-com-support-classes.md)   
 [IErrorInfo arabirimi](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)