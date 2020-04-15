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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 0f0a3ea3e1f2e43d53650b4017905c696269ce20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343939"
---
# <a name="_invalid_parameter-_invalid_parameter_noinfo-_invalid_parameter_noinfo_noreturn-_invoke_watson"></a>_invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson

Bu işlevler, CRT Kitaplığı işlevlerine geçirilen geçerli olmayan parametreleri işlemek için C Runtime Kitaplığı tarafından kullanılır. Kodunuz bu işlevleri varsayılan veya geçerli olmayan parametrelerin özelleştirilebilir şekilde işlenmesini desteklemek için de kullanabilir.

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

*Ifa -de*<br/>
Geçerli olmayan kaynak kodu parametre ifadesini temsil eden bir dize.

*function_name*<br/>
İşleyici yi çağıran işlevin adı.

*Dosya_adı*<br/>
İşleyicinin çağrıldığı kaynak kod dosyası.

*line_number*<br/>
İşleyicinin çağrıldığı kaynak kodundaki satır numarası.

*Saklı -dır*<br/>
Kullanılmıyor.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevler bir değer döndürmez. **_invalid_parameter_noinfo_noreturn** ve **_invoke_watson** işlevleri arayana dönmez ve bazı durumlarda **_invalid_parameter** ve **_invalid_parameter_noinfo** arayanın geri dönemeyebileceğiz.

## <a name="remarks"></a>Açıklamalar

C çalışma zamanı kitaplığı işlevleri geçerli olmayan parametreler geçirildiğinde, kitaplık işlevleri geçersiz bir *parametre işleyicisi*, programcı tarafından birkaç şey yapmak için belirtilmiş olabilir bir işlev çağırır. Örneğin, sorunu kullanıcıya bildirebilir, bir günlüğe yazabilir, hata ayıklayıcıyı kırabilir, programı sonlandırabilir veya hiçbir şey yapmaabilir. Programcı tarafından işlev belirtilmemişse, varsayılan işleyici, **_invoke_watson**, çağrılır.

Varsayılan olarak, hata ayıklama kodunda geçerli olmayan bir parametre tanımlandığında, CRT kitaplık işlevleri ayrıntılı parametreleri kullanarak işlevi **_invalid_parameter** çağırır. Hata ayıklama kodunda, boş parametreleri kullanarak **_invalid_parameter** işlevini çağıran **_invalid_parameter_noinfo** işlevi çağrılır. Hata ayıklama olmayan CRT kitaplık işlevi program sonlandırma gerektiriyorsa, **_invalid_parameter_noinfo_noreturn** işlevi denir, boş parametreleri kullanarak **_invalid_parameter** işlevi çağırır, ardından program sonlandırma zorlamak için **_invoke_watson** işlevine bir çağrı.

**_invalid_parameter** işlevi, kullanıcı tanımlı geçersiz parametre işleyicisinin ayarlanıp ayarlanmadığını denetler ve eğer öyleyse, onu çağırır. Örneğin, kullanıcı tanımlı iş parçacığı yerel işleyicisi geçerli iş parçacığı [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) için bir çağrı tarafından ayarlanmışsa, denir, sonra işlev döndürür. Aksi takdirde, kullanıcı tanımlı bir genel geçersiz parametre [işleyicisi set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)için bir çağrı tarafından ayarlanmışsa, denir, sonra işlev döndürür. Aksi takdirde, varsayılan işleyici **_invoke_watson** çağrılır. **_invoke_watson** varsayılan davranışı programı sonlandırmaktır. Kullanıcı tanımlı işleyiciler sonlandırılabilir veya geri dönebilir. Kurtarma kesin olmadığı sürece kullanıcı tanımlı işleyicilerin programı sonlandırmasını öneririz.

Varsayılan işleyici **_invoke_watson** çağrıldığında, işlemci [__fastfail](../../intrinsics/fastfail.md) bir işlemi destekliyorsa, **FAST_FAIL_INVALID_ARG** parametresi kullanılarak çağrılır ve işlem sonlanır. Aksi takdirde, ekli bir hata ayıklama tarafından yakalanabilir hızlı bir başarısız özel durum yükseltilir. İşlemin devam etmesine izin verilirse, windows **terminateprocess** işlevine yapılan bir çağrı yla **STATUS_INVALID_CRUNTIME_PARAMETER**özel durum kodu durumu kullanılarak sonlandırılır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|------------------|
|**_invalid_parameter**, **_invalid_parameter_noinfo**, **_invalid_parameter_noinfo_noreturn**, **_invoke_watson**|\<corecrt.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)<br/>
