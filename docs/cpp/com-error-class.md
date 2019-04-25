---
title: _com_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- _com_error
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
ms.openlocfilehash: 8ed1521cbf768e5b473281e5f9b7c6597cdc4692
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155208"
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
|[Hata:](../cpp/com-error-error.md)|Oluşturucuya geçirilen HRESULT alır.|
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

[Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)<br/>
[IErrorInfo arabirimi](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)