---
description: 'Hakkında daha fazla bilgi edinin: _com_error sınıfı'
title: _com_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- _com_error
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
ms.openlocfilehash: 2d297da005feba39838679ed2b7062ce54ad9c38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318214"
---
# <a name="_com_error-class"></a>_com_error Sınıfı

**Microsoft'a Özgü**

**_Com_error** nesnesi, tür KITAPLıĞıNDAN veya com destek sınıflarından birinde oluşturulan üstbilgi dosyalarındaki hata işleme sarmalayıcı işlevleri tarafından algılanan bir özel durum koşulunu temsil eder. **_Com_error** sınıfı, hresult hata kodunu ve ilişkili tüm nesneleri kapsar `IErrorInfo Interface` .

### <a name="construction"></a>İnşaat

| Ad | Açıklama |
|-|-|
|[_com_error](../cpp/com-error-com-error.md)|**_Com_error** nesnesi oluşturur.|

### <a name="operators"></a>İşleçler

| Ad | Açıklama |
|-|-|
|[işleç =](../cpp/com-error-operator-equal.md)|Varolan bir **_com_error** nesnesini başka bir nesneye atar.|

### <a name="extractor-functions"></a>Extractor Işlevleri

| Ad | Açıklama |
|-|-|
|[Hata](../cpp/com-error-error.md)|Oluşturucuya geçirilen HRESULT 'yi alır.|
|[ErrorInfo](../cpp/com-error-errorinfo.md)|`IErrorInfo`Oluşturucuya geçirilen nesneyi alır.|
|[WCode](../cpp/com-error-wcode.md)|Encapsulated HRESULT 'e eşlenmiş 16 bit hata kodunu alır.|

### <a name="ierrorinfo-functions"></a>IErrorInfo Işlevleri

| Ad | Açıklama |
|-|-|
|[Açıklama](../cpp/com-error-description.md)|Çağıran `IErrorInfo::GetDescription` işlevi.|
|[HelpContext](../cpp/com-error-helpcontext.md)|Çağıran `IErrorInfo::GetHelpContext` işlevi.|
|[HelpFile](../cpp/com-error-helpfile.md)|Çağrılar `IErrorInfo::GetHelpFile` işlevi|
|[Kaynak](../cpp/com-error-source.md)|Çağıran `IErrorInfo::GetSource` işlevi.|
|['INI](../cpp/com-error-guid.md)|Çağıran `IErrorInfo::GetGUID` işlevi.|

### <a name="format-message-extractor"></a>Ileti ayıklayıcısı Biçimlendir

| Ad | Açıklama |
|-|-|
|[Hata](../cpp/com-error-errormessage.md)|**_Com_error** NESNESINDE depolanan HRESULT için dize iletisini alır.|

### <a name="exepinfowcode-to-hresult-mappers"></a>Exepınfo. wCode to HRESULT Mapto

| Ad | Açıklama |
|-|-|
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|32 bitlik HRESULT 'yi 16 bit 'e eşler `wCode` .|
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|16 bit `wCode` ile 32 BIT HRESULT eşler.|

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<comdef.h>

`Lib:` comsuppw. lib veya comsuppwd. lib (daha fazla bilgi için bkz. [/Zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM desteği sınıfları](../cpp/compiler-com-support-classes.md)<br/>
[IErrorInfo arabirimi](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)
