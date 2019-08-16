---
title: _com_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- _com_error
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
ms.openlocfilehash: 828a1ec68fef631700d5b64e6aeeec6660acf9a8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498739"
---
# <a name="_com_error-class"></a>_com_error Sınıfı

**Microsoft 'a özgü**

**_Com_error** nesnesi, tür KITAPLıĞıNDAN veya com destek sınıflarından birinde oluşturulan üstbilgi dosyalarındaki hata işleme sarmalayıcı işlevleri tarafından algılanan bir özel durum koşulunu temsil eder. **_Com_error** sınıfı, hresult hata kodunu ve ilişkili `IErrorInfo Interface` tüm nesneleri kapsar.

### <a name="construction"></a>İnşaat

|||
|-|-|
|[_com_error](../cpp/com-error-com-error.md)|Bir **_com_error** nesnesi oluşturur.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](../cpp/com-error-operator-equal.md)|Var olan bir **_com_error** nesnesini başka bir nesneye atar.|

### <a name="extractor-functions"></a>Extractor Işlevleri

|||
|-|-|
|[Hata:](../cpp/com-error-error.md)|Oluşturucuya geçirilen HRESULT 'yi alır.|
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Oluşturucuya geçirilen `IErrorInfo` nesneyi alır.|
|[WCode](../cpp/com-error-wcode.md)|Encapsulated HRESULT 'e eşlenmiş 16 bit hata kodunu alır.|

### <a name="ierrorinfo-functions"></a>IErrorInfo Işlevleri

|||
|-|-|
|[Açıklama](../cpp/com-error-description.md)|Çağıran `IErrorInfo::GetDescription` işlevi.|
|[HelpContext](../cpp/com-error-helpcontext.md)|Çağıran `IErrorInfo::GetHelpContext` işlevi.|
|[HelpFile](../cpp/com-error-helpfile.md)|Çağrılar `IErrorInfo::GetHelpFile` işlevi|
|[Kaynak](../cpp/com-error-source.md)|Çağıran `IErrorInfo::GetSource` işlevi.|
|[GUID](../cpp/com-error-guid.md)|Çağıran `IErrorInfo::GetGUID` işlevi.|

### <a name="format-message-extractor"></a>Ileti ayıklayıcısı Biçimlendir

|||
|-|-|
|[Hata](../cpp/com-error-errormessage.md)|**_Com_error** NESNESINDE depolanan HRESULT için dize iletisini alır.|

### <a name="exepinfowcode-to-hresult-mappers"></a>Exepınfo. wCode to HRESULT Mapto

|||
|-|-|
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|32 bitlik HRESULT 'yi 16 bit `wCode`'e eşler.|
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|16 bit `wCode` ile 32 bit HRESULT eşler.|

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Comdef. h >

`Lib:`comsuppw. lib veya comsuppwd. lib (daha fazla bilgi için bkz. [/Zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)<br/>
[IErrorInfo arabirimi](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)