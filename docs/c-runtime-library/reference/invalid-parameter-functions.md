---
title: _invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson
ms.date: 11/04/2016
apiname:
- _invalid_parameter
- _invalid_parameter_noinfo
- _invalid_parameter_noinfo_noreturn
- _invoke_watson
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: e43d5caaeebb6303d209d870c804357117812985
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478370"
---
# <a name="invalidparameter-invalidparameternoinfo-invalidparameternoinfonoreturn-invokewatson"></a>_invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson

Bu işlevler C çalışma zamanı kitaplığı tarafından CRT kitaplık işlevleri için geçirilen geçerli olmayan parametre işlemek için kullanılır. Kodunuzu bu işlevlerin, varsayılan veya geçerli olmayan parametreler özelleştirilebilir işlenmesini desteklemek için de kullanabilirsiniz.

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

*İfade*<br/>
Geçersiz kaynak kodu parametresi ifadeyi temsil eden bir dize.

*işlev_adı*<br/>
Çağrılan işleyici işlevinin adı.

*file_name*<br/>
Kaynak kodu dosyasının nerede işleyici çağrıldı.

*line_number*<br/>
Burada işleyicisi çağrılmadan kaynak kodundaki satır numarası.

*Ayrılmış*<br/>
Kullanılmayan.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin bir değer döndürmeyen. **_İnvalid_parameter_noinfo_noreturn** ve **_invoke_watson** işlevleri çağıran ve bazı durumlarda, döndürmeyen **_invalid_parameter** ve **_invalid_parameter_noinfo** çağırana döndürmeyebilir.

## <a name="remarks"></a>Açıklamalar

C çalışma zamanı kitaplık işlevleri geçerli olmayan parametre olarak geçirildiğinde, çağrı kitaplığı işlevleri bir *geçersiz parametre işleyicisi*, birkaç şey birini yapmak için Programcı tarafından belirtilen bir işlev. Örneğin, bu kullanıcıya sorunu bildirin, günlüğe yazma, bir hata ayıklayıcıda kesme, programı sonlandırmak veya hiç hiçbir şey yapma. Hiçbir işlev Programcı tarafından bir varsayılan işleyici olarak belirtilirse **_invoke_watson**, çağrılır.

Varsayılan olarak, geçerli olmayan bir parametre kodu hata ayıklama belirlendiğinde CRT kitaplığı işlevleri işlevi çağırabilir. **_invalid_parameter** ayrıntılı parametreleri kullanarak. Hata ayıklama olmayan kodda, **_invalid_parameter_noinfo** işlevi çağrılır, çağıran **_invalid_parameter** boş parametreleri kullanarak bu işlevi. Program sonlandırma olmayan hata ayıklama CRT kitaplığı işlevi gerektiriyorsa, **_invalid_parameter_noinfo_noreturn** işlevi çağrılır, çağıran **_invalid_parameter** boş kullanarak bu işlevi parametreleri, ardından bir çağrı tarafından **_invoke_watson** program sonlandırma zorlamak için işlevi.

**_İnvalid_parameter** işlevi denetimleri bir kullanıcı tanımlı geçersiz parametre işleyicisi ayarlanmış olup olmadığını ve bu durumda, çağırır. Örneğin, kullanıcı tanımlı bir iş parçacığı-yerel işleyici için bir çağrı tarafından ayarlanmışsa [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) geçerli iş parçacığı adlandırılır ve işlev döndürür. Aksi takdirde bir çağrı tarafından bir kullanıcı tarafından tanımlanan genel geçersiz parametre işleyicisi ayarlandıysa [set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)çağrılır, ardından işlev döndürür. Aksi takdirde, varsayılan işleyici **_invoke_watson** çağrılır. Varsayılan davranışını **_invoke_watson** Programı sonlandırmak için. Kullanıcı tanımlı işleyiciler sonlandırmak veya döndürür. Kullanıcı tanımlı işleyiciler kurtarma belirli olmadığı sürece Programı sonlandırmak öneririz.

Varsayılan işleyici **_invoke_watson** çağrılır, işlemci destekliyorsa bir [__fastfail](../../intrinsics/fastfail.md) işlem parametresi kullanılarak çağrılır **FAST_FAIL_INVALID_ARG** ve işlemi sonlandırır. Aksi takdirde, ekli bir hata ayıklayıcı tarafından yakalanabilir bir hızlı hata özel durum oluşturulur. İşlemin devam etmesine izin verilirse, Windows için bir çağrı tarafından sonlandırılır **TerminateProcess** bir özel durum kodu durumunu kullanarak bu işlevi **STATUS_INVALID_CRUNTIME_PARAMETER**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|------------------|
|**_invalid_parameter**, **_invalid_parameter_noinfo**, **_invalid_parameter_noinfo_noreturn**, **_invoke_watson**|\<corecrt.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)<br/>
