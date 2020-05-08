---
title: _invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson
ms.date: 4/2/2020
api_name:
- _invalid_parameter
- _invalid_parameter_noinfo
- _invalid_parameter_noinfo_noreturn
- _invoke_watson
- _o__invalid_parameter_noinfo
- _o__invalid_parameter_noinfo_noreturn
api_location:
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CORECRT/_invalid_parameter
- _invalid_parameter
- CORECRT/_invalid_parameter_noinfo
- _invalid_parameter_noinfo
- CORECRT/_invalid_parameter_noinfo_noreturn
- _invalid_parameter_noinfo_noreturn
- CORECRT/_invoke_watson
- _invoke_watson
ms.assetid: a4d6f1fd-ce56-4783-8719-927151a7a814
ms.openlocfilehash: 7138e9cb7381e4d40911054e1473536b6e639e2d
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919831"
---
# <a name="_invalid_parameter-_invalid_parameter_noinfo-_invalid_parameter_noinfo_noreturn-_invoke_watson"></a>_invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson

Bu işlevler, CRT kitaplığı işlevlerine geçirilen geçerli olmayan parametreleri işlemek için C çalışma zamanı kitaplığı tarafından kullanılır. Kodunuz, geçerli olmayan parametrelerin varsayılan veya özelleştirilebilir işlemesini desteklemek için de bu işlevleri kullanabilir.

## <a name="syntax"></a>Sözdizimi

```C
extern "C" void __cdecl
_invalid_parameter(
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);

extern "C" void __cdecl
_invalid_parameter_noinfo(void);

extern "C" __declspec(noreturn) void __cdecl
_invalid_parameter_noinfo_noreturn(void);

extern "C" __declspec(noreturn) void __cdecl
_invoke_watson(
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);
```

## <a name="parameters"></a>Parametreler

*ifadesini*<br/>
Geçerli olmayan kaynak kodu parametre ifadesini temsil eden bir dize.

*function_name*<br/>
İşleyiciyi çağıran işlevin adı.

*file_name*<br/>
İşleyicinin çağrıldığı kaynak kodu dosyası.

*line_number*<br/>
İşleyicinin çağrıldığı kaynak kodundaki satır numarası.

*ayrılamadı*<br/>
Kullanılmıyor.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevler bir değer döndürmez. **_İnvalid_parameter_noinfo_noreturn** ve **_invoke_watson** işlevleri çağırana geri dönmez ve bazı durumlarda **_invalid_parameter** ve **_invalid_parameter_noinfo** çağırana geri dönemeyebilir.

## <a name="remarks"></a>Açıklamalar

C çalışma zamanı kitaplığı işlevleri geçerli olmayan parametreler geçirildiğinde, kitaplık işlevleri, programcı tarafından birkaç şeyi yapmak üzere belirtilemeyen bir işlev olan *geçersiz bir parametre işleyicisini*çağırır. Örneğin, sorunu kullanıcıya bildirebilir, bir günlüğe yazabilir, bir hata ayıklayıcıda kesilebilir, programı sonlandırabilir veya hiçbir şey yapmayabilir. Programcı tarafından hiçbir işlev belirtilmemişse, **_invoke_watson**varsayılan işleyicisi çağrılır.

Varsayılan olarak, hata ayıklama kodunda geçerli olmayan bir parametre tanımlandığında CRT kitaplığı işlevleri, ayrıntılı parametreleri kullanarak işlevi **_invalid_parameter** çağırır. Hata ayıklama olmayan kodda, boş parametreler kullanarak **_invalid_parameter** işlevini çağıran **_invalid_parameter_noinfo** işlevi çağırılır. Hata ayıklama olmayan CRT kitaplığı işlevi program sonlandırmasını gerektiriyorsa, **_invalid_parameter_noinfo_noreturn** işlevi çağrılır, bu, boş parametreler kullanılarak **_invalid_parameter** işlevini çağırır ve sonra program sonlandırmasını zorlamak için **_invoke_watson** işlevine yapılan bir çağrıdır.

**_İnvalid_parameter** işlevi, Kullanıcı tanımlı geçersiz parametre işleyicisinin ayarlanmış olup olmadığını denetler ve varsa onu çağırır. Örneğin, Kullanıcı tanımlı bir iş parçacığı yerel işleyicisi geçerli iş parçacığında [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) çağrısıyla ayarlandıysa, çağrılır, sonra işlev döndürülür. Aksi halde, Kullanıcı tanımlı bir genel geçersiz parametre işleyicisi [set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)çağrısıyla ayarlandıysa, çağrılır, sonra işlev döndürülür. Aksi takdirde, varsayılan işleyici **_invoke_watson** çağırılır. **_İnvoke_watson** varsayılan davranışı programı sonlandıracaktır. Kullanıcı tanımlı işleyiciler sonlandırılabilir veya geri dönebilir. Kurtarma belirli değilse, Kullanıcı tanımlı işleyicilerin programı sonlanmasını öneririz.

Varsayılan işleyici **_invoke_watson** çağrıldığında, işlemci bir [__fastfail](../../intrinsics/fastfail.md) işlemini destekliyorsa, bir **FAST_FAIL_INVALID_ARG** parametresi kullanılarak çağrılır ve işlem sonlandırılır. Aksi takdirde, ekli bir hata ayıklayıcı tarafından yakalanabilecek hızlı bir hata özel durumu oluşturulur. İşlemin devam etmesine izin veriliyorsa, **STATUS_INVALID_CRUNTIME_PARAMETER**özel durum kodu kullanılarak Windows **TerminateProcess** işlevine yapılan bir çağrı tarafından sonlandırılır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|------------------|
|**_invalid_parameter**, **_invalid_parameter_noinfo**, **_invalid_parameter_noinfo_noreturn**, **_invoke_watson**|\<corecrt. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[Parametre doğrulama](../../c-runtime-library/parameter-validation.md)<br/>
