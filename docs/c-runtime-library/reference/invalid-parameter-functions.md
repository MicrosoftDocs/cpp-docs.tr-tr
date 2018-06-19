---
title: _invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b0fecd7eefe9ac6a7a479fb12475b2b1c769cf4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405477"
---
# <a name="invalidparameter-invalidparameternoinfo-invalidparameternoinfonoreturn-invokewatson"></a>_invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson

Bu işlevler tarafından C çalışma zamanı kitaplığı CRT kitaplık, işlevlere geçirilen geçerli olmayan parametreleri işlemek için kullanılır. Kodunuzu varsayılan veya geçerli olmayan parametreler özelleştirilebilir işlenmesini desteklemek için bu işlevler de kullanabilirsiniz.

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

*ifade* geçersiz kaynak kod parametre ifadesi temsil eden dize.

*işlev_adı* işleyici adlı işlevin adı.

*dosya_adı* işleyici burada çağrıldı kaynak kodu dosyasının.

*line_number* işleyici burada çağrıldı kaynak kodunda satır numarası.

*ayrılmış* kullanılmıyor.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin bir dönüş değeri değil. **_İnvalid_parameter_noinfo_noreturn** ve **_invoke_watson** işlevleri çağırana ve bazı durumlarda, döndürmeyen **_invalid_parameter** ve **_invalid_parameter_noinfo** çağırana döndürmeyebilir.

## <a name="remarks"></a>Açıklamalar

C çalışma zamanı kitaplığı işlevleri geçerli olmayan parametreler geçirildiğinde çağrısı kitaplık işlevleri bir *geçersiz parametre işleyicisi*, birkaç şey birini yapmak için Programcı tarafından belirtilen bir işlev. Örneğin, bunu kullanıcıya sorunu bildirin, günlüğe yazma, bir hata ayıklayıcıda bölün, programı sonlandırmak veya hiç yapmıyor. Hiçbir işlev Programcı, varsayılan işleyici tarafından belirtilmişse **_invoke_watson**, olarak adlandırılır.

Varsayılan olarak, geçerli olmayan bir parametre hata ayıklama kodda tanımlandığında CRT kitaplık işlevleri işlevi çağırın. **_invalid_parameter** ayrıntılı parametrelerini kullanarak. Hata ayıklama olmayan kodda **_invalid_parameter_noinfo** işlevi çağrıldığında, çağıran **_invalid_parameter** boş parametrelerini kullanarak işlev. Hata ayıklama olmayan CRT kitaplık işlevi program sonlandırma gerektiriyorsa **_invalid_parameter_noinfo_noreturn** işlevi çağrıldığında, çağıran **_invalid_parameter** boş kullanarak işlevi parametre için bir çağrı tarafından izlenen **_invoke_watson** program sonlandırma zorlamak için işlevi.

**_İnvalid_parameter** işlevi denetimleri bir kullanıcı tarafından tanımlanan geçersiz parametre işleyicisi ayarlanmış olup olmadığını ve bu durumda, çağırır. Örneğin, bir kullanıcı tarafından tanımlanan iş parçacığı yerel işleyici için bir çağrı tarafından ayarlanmışsa [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) geçerli iş parçacığının adlı sonra işlevi döndürür. Aksi durumda, bir kullanıcı tarafından tanımlanan genel geçersiz parametre işleyicisi için bir çağrı tarafından ayarlanmışsa [set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)adı verilir ve ardından işlevi döndürür. Aksi takdirde, varsayılan işleyici **_invoke_watson** olarak adlandırılır. Varsayılan davranışını **_invoke_watson** Programı sonlandırmak için. Kullanıcı tanımlı işleyiciler sonlandırma dönün veya. Kurtarma belirli olmadığı sürece kullanıcı tanımlı işleyiciler Programı sonlandırmak öneririz.

Varsayılan işleyici **_invoke_watson** çağrılır, işlemci destekliyorsa, bir [__fastfail](../../intrinsics/fastfail.md) işlemi, bir parametresi kullanılarak çağrılır **FAST_FAIL_INVALID_ARG** ve işlemi sonlandırır. Aksi durumda, ekli bir hata ayıklayıcı tarafından yakalanabilir hızlı hata özel durum oluşturulur. İşlem devam etmek için izin veriliyorsa, Windows için bir çağrı tarafından sonlandırılır **TerminateProcess** bir özel durum kodu durumunu kullanarak işlev **STATUS_INVALID_CRUNTIME_PARAMETER**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|------------------|
|**_invalid_parameter**, **_invalid_parameter_noinfo**, **_invalid_parameter_noinfo_noreturn**, **_invoke_watson**|\<corecrt.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)<br/>
