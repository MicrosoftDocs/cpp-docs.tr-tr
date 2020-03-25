---
title: _com_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- _com_error
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
ms.openlocfilehash: 0c33791fbe6011a3eddc6e535a3a4ed838e5e06c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180816"
---
# <a name="_com_error-class"></a>_com_error Sınıfı

**Microsoft 'a özgü**

**_Com_error** nesnesi, tür KITAPLıĞıNDAN veya com destek sınıflarından birinde oluşturulan üstbilgi dosyalarındaki hata işleme sarmalayıcı işlevleri tarafından algılanan bir özel durum koşulunu temsil eder. **_Com_error** sınıfı, hresult hata kodunu ve ilişkili tüm `IErrorInfo Interface` nesnelerini kapsüller.

### <a name="construction"></a>İnşaat

|||
|-|-|
|[_com_error](../cpp/com-error-com-error.md)|**_Com_error** nesnesi oluşturur.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](../cpp/com-error-operator-equal.md)|Varolan bir **_com_error** nesnesini başka bir nesneye atar.|

### <a name="extractor-functions"></a>Extractor Işlevleri

|||
|-|-|
|[Hata](../cpp/com-error-error.md)|Oluşturucuya geçirilen HRESULT 'yi alır.|
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Oluşturucuya geçirilen `IErrorInfo` nesnesini alır.|
|[WCode](../cpp/com-error-wcode.md)|Encapsulated HRESULT 'e eşlenmiş 16 bit hata kodunu alır.|

### <a name="ierrorinfo-functions"></a>IErrorInfo Işlevleri

|||
|-|-|
|[Açıklama](../cpp/com-error-description.md)|`IErrorInfo::GetDescription` işlevini çağırır.|
|[HelpContext](../cpp/com-error-helpcontext.md)|`IErrorInfo::GetHelpContext` işlevini çağırır.|
|[HelpFile](../cpp/com-error-helpfile.md)|`IErrorInfo::GetHelpFile` işlevini çağırır|
|[Kaynak](../cpp/com-error-source.md)|`IErrorInfo::GetSource` işlevini çağırır.|
|['INI](../cpp/com-error-guid.md)|`IErrorInfo::GetGUID` işlevini çağırır.|

### <a name="format-message-extractor"></a>Ileti ayıklayıcısı Biçimlendir

|||
|-|-|
|[Hata](../cpp/com-error-errormessage.md)|**_Com_error** NESNESINDE depolanan HRESULT için dize iletisini alır.|

### <a name="exepinfowcode-to-hresult-mappers"></a>Exepınfo. wCode to HRESULT Mapto

|||
|-|-|
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|32 bit HRESULT ile 16 bit `wCode`eşler.|
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|16 bit `wCode` 32 bit HRESULT 'e eşler.|

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<Comdef. h >

`Lib:` comsuppw. lib veya comsuppwd. lib (daha fazla bilgi için bkz. [/Zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)<br/>
[IErrorInfo arabirimi](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)
