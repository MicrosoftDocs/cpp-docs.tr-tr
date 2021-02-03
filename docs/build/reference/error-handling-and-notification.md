---
title: Hata işleme ve bildirme
description: 'Hakkında daha fazla bilgi edinin: DLL Gecikmeli yükleme hatası işleme ve bildirim'
ms.date: 01/19/2021
helpviewer_keywords:
- error handling, and notification
ms.openlocfilehash: efff7ba9956bee8fe6ccf1df96a3f4b49852ce43
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522566"
---
# <a name="error-handling-and-notification"></a>Hata işleme ve bildirme

Programınız Gecikmeli yüklenen dll 'Ler kullanıyorsa, program çalışırken meydana gelen hatalar işlenmemiş özel durumlara neden olacağı için robustly hataları işlemelidir. Hata işleme iki bölümden oluşur: bir kanca üzerinden kurtarma ve bir özel durum aracılığıyla raporlama.

DLL gecikmesi yükleme hatası işleme ve bildirimi hakkında daha fazla bilgi için bkz. [yardımcı Işlevini anlama](understanding-the-helper-function.md).

Kanca işlevleri hakkında daha fazla bilgi için bkz. [Yapı ve sabit tanımlar](understanding-the-helper-function.md#structure-and-constant-definitions).

## <a name="recovery-through-a-hook"></a>Kanca üzerinden kurtarma

Kodunuzun bir hata üzerinde kurtarılması veya alternatif bir kitaplık ya da yordam sağlaması gerekebilir. Yardımcı işleve, alternatif kodu sağlayabilecek veya durumu ortadan kaldırmanın bir kancasını sağlayabilirsiniz. Kanca yordamının uygun bir değer döndürmesi gerekir, böylece işlem devam edebilir (bir `HINSTANCE` veya `FARPROC` ). Ya da bir özel durumun oluşturulması gerektiğini göstermek için 0 döndürebilir. Ayrıca kendi özel durumunu veya `longjmp` kancasını de oluşturabilir. Bildirim kancaları ve hata kancaları vardır. Aynı yordam her ikisi için de kullanılabilir.

## <a name="notification-hooks"></a><a name="notification-hooks"></a> Bildirim kancaları

Gecikme yükü bildirim kancaları, aşağıdaki eylemler yardımcı yordamında alınmadan hemen önce çağrılır:

- Kitaplığın saklı tanıtıcısı, zaten yüklenmiş olup olmadığını görmek üzere denetlenir.

- `LoadLibrary` , DLL 'nin yükünü denemek için çağırılır.

- `GetProcAddress` yordamın adresini almayı denemek için çağırılır.

- Gecikmeli içeri aktarma yükleme Dönüştürücüsü ' ne dönün.

Bildirim kancası etkin:

- Bir işaretçinin, `__pfnDliNotifyHook2` bildirimleri alan kendi işlevinizi işaret etmek üzere başlatılmış yeni bir tanımını sağlayarak.

   \-veya

- İşaretçiyi, `__pfnDliNotifyHook2` DLL 'ye yapılan herhangi bir çağrının yükleme gecikmesi olduğu herhangi bir çağrısından önce kanca işleviniz olarak ayarlayarak.

Bildirim ise `dliStartProcessing` , kanca işlevi şu şekilde dönebilir:

- `NULL`

   Varsayılan yardımcı, DLL yüklemesini işler. Yalnızca bilgilendirme amacıyla çağırmak yararlı olur.

- bir işlev işaretçisi

   Varsayılan Gecikmeli yükleme işlemesini atlayın. Kendi yük işleyicinizi sağlamanıza olanak tanır.

Bildirim ise `dliNotePreLoadLibrary` , kanca işlevi şu şekilde dönebilir:

- yalnızca bilgilendirme bildirimleri istiyorsa 0.

- `HMODULE`Yüklenen dll için, DLL kendisini yükleirse.

Bildirim ise `dliNotePreGetProcAddress` , kanca işlevi şu şekilde dönebilir:

- yalnızca bilgilendirme bildirimleri istiyorsa 0.

- Kanca işlevi adresin kendisini alırsa, içeri aktarılan işlevin adresi.

Bildirim ise `dliNoteEndProcessing` , kanca işlevinin dönüş değeri yok sayılır.

Bu işaretçi başlatılmışsa (sıfır dışında), Gecikmeli Yükleme Yardımcısı işlevi, yürütme boyunca belirli bildirim noktalarında çağırır. İşlev işaretçisi aşağıdaki tanıma sahiptir:

```C
// The "notify hook" gets called for every call to the
// delay load helper.  This allows a user to hook every call and
// skip the delay load helper entirely.
//
// dliNotify == {
//  dliStartProcessing |
//  dliNotePreLoadLibrary  |
//  dliNotePreGetProc |
//  dliNoteEndProcessing}
//  on this call.
//
ExternC
PfnDliHook   __pfnDliNotifyHook2;

// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

Bildirimler, `DelayLoadInfo` bildirim değeriyle birlikte kanca işlevine bir yapıda geçer. Bu veriler, gecikme Yükleme Yardımcısı yordamının kullandığı verilerle aynıdır. Bildirim değeri, [Yapı ve sabit tanımlarda](understanding-the-helper-function.md#structure-and-constant-definitions)tanımlanan değerlerden biri olacaktır.

## <a name="failure-hooks"></a><a name="failure-hooks"></a> Hata kancaları

Hata kancası, [bildirim kancası](#notification-hooks)ile aynı şekilde etkindir. `HINSTANCE`Bir özel durumun oluşturulması gerektiğini belirtmek için, kanca yordamının uygun bir değer döndürmesi gerekir, böylece işlem devam edebilir (bir veya `FARPROC` ) ya da 0.

Kullanıcı tanımlı işleve başvuran işaretçi değişkeni:

```C
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

**`DelayLoadInfo`** Yapı, hata hakkında ayrıntılı raporlama için gereken tüm verileri içerir, örneğin değeri de dahildir `GetLastError` .

Bildirim ise **`dliFailLoadLib`** , kanca işlevi şu şekilde dönebilir:

- 0, hatayı işleyemeyebilir.

- `HMODULE`, Hata kancasını sorunu düzeltti ve kitaplığın kendisini yükleirse.

Bildirim ise **`dliFailGetProc`** , kanca işlevi şu şekilde dönebilir:

- 0, hatayı işleyemeyebilir.

- Başarısız olan bir proc adresi (alma işlevi adresi), adresin kendisini alma işleminde başarılı oldu.

## <a name="report-by-using-an-exception"></a>Özel durum kullanarak raporla

Hatayı işlemek için gerekli olan tüm işlemler yordamı iptal etmek ise, Kullanıcı kodu özel durumu işleyebileceği sürece hiçbir kanca gerekmez.

## <a name="delay-load-exception-codes"></a><a name="delay-load-exception-codes"></a> Gecikme yükleme özel durum kodları

Bir Gecikmeli yük sırasında hata oluştuğunda yapılandırılmış özel durum kodları oluşturulabilir. Özel durum değerleri bir makro kullanılarak belirtilir `VcppException` :

```C
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

Bir `LoadLibrary` hata için standart `VcppException(ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND)` oluşturulur. Hata için `GetProcAddress` , oluşan hata `VcppException(ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND)` . Özel durum bir yapıya işaretçi geçirir `DelayLoadInfo` . Bu, `LPDWORD` `GetExceptionInformation` [`EXCEPTION_RECORD`](/windows/win32/api/winnt/ns-winnt-exception_record) alanındaki yapıdan alınan değerde `ExceptionInformation[0]` .

Alanda yanlış bitler ayarlandıysa `grAttrs` , özel durum `ERROR_INVALID_PARAMETER` oluşturulur. Bu özel durum, tüm amaçlar ve amaçlar için önemli.

Daha fazla bilgi için bkz. [Yapı ve sabit tanımlar](understanding-the-helper-function.md#structure-and-constant-definitions).

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli yüklenen DLL'ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)
