---
description: Gecikme Yükleme Yardımcısı işlevi hakkında daha fazla bilgi edinin
title: Gecikme yükleme yardımcısı işlevini anlayın
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.openlocfilehash: 6108e896b6d7a370f2b4d6ab8f5baa880112a21e
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522748"
---
# <a name="understand-the-delay-load-helper-function"></a>Gecikme yükleme yardımcısı işlevini anlayın

Bağlayıcı için yardımcı işlev-desteklenen Gecikmeli yükleme, çalışma zamanında DLL 'yi gerçekten yükler. Davranışını özelleştirmek için yardımcı işlevini değiştirebilirsiniz. İçinde sağlanan yardımcı işlevini kullanmak yerine *`delayimp.lib`* kendi işlevinizi yazın ve programınıza bağlayın. Bir yardımcı işlev, tüm Gecikmeli yüklenen dll 'Leri sunar.

DLL veya içeri aktarmalar adına göre belirli işlemler yapmak istiyorsanız, kendi yardımcı işlevinizin bir sürümünü sağlayabilirsiniz.

Yardımcı işlevi şu işlemleri gerçekleştirir:

- Zaten yüklenmiş olup olmadığını görmek için kitaplığa depolanmış tanıtıcıyı denetler

- `LoadLibrary`DLL yüklemeyi denemek için çağrılar

- `GetProcAddress`Yordamın adresini almayı denemek için çağrılar

- Şimdi yüklenen giriş noktasını çağırmak için Gecikmeli içeri aktarma yük dönüşmesini döndürür

Yardımcı işlevi, aşağıdaki eylemlerden her birini gerçekleştirdikten sonra programınızdaki bir bildirim kancasını geri çağırabilir:

- Yardımcı işlev başladığında

- `LoadLibrary`Yardımcı işlevinde yalnızca Before çağrılır

- `GetProcAddress`Yardımcı işlevinde yalnızca Before çağrılır

- `LoadLibrary`Yardımcı işlevindeki çağrısı başarısız olursa

- `GetProcAddress`Yardımcı işlevindeki çağrısı başarısız olursa

- Yardımcı işlevi işlemi tamamlandıktan sonra

Bu kanca noktalarından her biri, gecikme içeri aktarma yük dönüşöğesine geri dönmesinin dışında, yardımcı yordamın normal işlemesini bir şekilde değiştiren bir değer döndürebilir.

Varsayılan yardımcı kodu *`delayhlp.cpp`* MSVC dizininde ve içinde bulunabilir *`delayimp.h`* *`include`* . *`delayimp.lib`* *`lib`* Hedef MIMARINIZ için MSVC dizininde derlenir. Kendi yardımcı işlevinizi yazmadığınız takdirde bu kitaplığı derlemelerine eklemeniz gerekir.

## <a name="delay-load-helper-calling-conventions-parameters-and-return-type"></a><a name="calling-conventions-parameters-and-return-type"></a> Kuralları, parametreleri ve dönüş türünü çağıran yük yardımcısını geciktir

Gecikme Yükleme Yardımcısı yordamının prototipi şunlardır:

```C
FARPROC WINAPI __delayLoadHelper2(
    PCImgDelayDescr pidd,
    FARPROC * ppfnIATEntry
);
```

### <a name="parameters"></a>Parametreler

*`pidd`*\
**`const`** `ImgDelayDescr` İçeri aktarma ile ilgili çeşitli verileri, bağlama bilgileri için zaman damgasını ve tanımlayıcı içeriği hakkında daha fazla bilgi sağlayan bir öznitelik kümesini içeren bir işaretçisi. Şu anda, `dlattrRva` Tanımlayıcıdaki adreslerin göreli sanal adresler olduğunu gösteren yalnızca bir öznitelik vardır. Daha fazla bilgi için içindeki bildirimlere bakın *`delayimp.h`* .

Gecikme Tanımlayıcıdaki işaretçiler ( `ImgDelayDescr` içindeki), *`delayimp.h`* 32-bit ve 64 bit programlarda beklenen şekilde çalışması için göreli sanal adresler (RVA) kullanır. Bunları kullanmak için, içinde bulunan işlevini kullanarak bu RVA öğesini işaretçilere geri dönüştürün `PFromRva` *`delayhlp.cpp`* . Bu işlevi, Tanımlayıcıdaki her bir alandan 32 bit ya da 64-bit işaretçilerine geri dönüştürmek için kullanabilirsiniz. Varsayılan Gecikmeli Yükleme Yardımcısı işlevi, örnek olarak kullanmak için iyi bir şablondur.

Yapının tanımı için `PCImgDelayDescr` bkz. [Yapı ve sabit tanımlar](#structure-and-constant-definitions).

*`ppfnIATEntry`*\
Gecikme yükleme içeri aktarma adres tablosundaki (ıAT) bir yuva işaretçisi. Bu, içeri aktarılan işlevin adresiyle güncelleştirilmiş olan yuvadadır. Yardımcı yordamının bu konuma döndürdüğü değeri aynı şekilde depolaması gerekir.

### <a name="expected-return-values"></a>Beklenen dönüş değerleri

Yardımcı işlev başarılı olursa, içeri aktarılan işlevin adresini döndürür.

İşlev başarısız olursa, yapılandırılmış bir özel durum oluşturur ve 0 döndürür. Üç tür özel durum oluşturulabilir:

- ' Deki öznitelikler doğru belirtilmediyse, geçersiz parametre *`pidd`* . Bunu kurtarılamaz bir hata olarak değerlendirin.

- `LoadLibrary` Belirtilen DLL 'de başarısız oldu.

- Hata `GetProcAddress` .

Bu özel durumları işlemek sizin sorumluluğunuzdadır. Daha fazla bilgi için bkz. [hata işleme ve bildirim](error-handling-and-notification.md).

### <a name="remarks"></a>Açıklamalar

Yardımcı işlevi için çağırma kuralı **`__stdcall`** . Dönüş değerinin türü ilgili değildir, bu nedenle `FARPROC` kullanılır. Bu işlev, C bağlantısına sahiptir ve bu, `extern "C"` C++ kodunda bildirildiği sırada sarmalanması gereken anlamına gelir. `ExternC`Makro sizin için bu sarmalayıcı ile ilgilenmelidir.

Yardımcı yordamlarınızı bir bildirim kancası olarak kullanmak için, kodunuzun döndürülecek uygun işlev işaretçisini belirtmesi gerekir. Bağlayıcının oluşturduğu dönüştürücü kodu, bu dönüş değerini içeri aktarmanın gerçek hedefi olarak alır ve doğrudan ona atlar. Yardımcı yordamlarınızı bir bildirim kancası olarak kullanmak istemiyorsanız, içindeki yardımcı işlevin dönüş değerini `ppfnIATEntry` , geçirilen işlev işaretçisi konumu olarak depolayın.

## <a name="sample-hook-function"></a>Örnek kanca işlevi

Aşağıdaki kod, temel bir kanca işlevinin nasıl uygulanacağını gösterir.

```C
FARPROC WINAPI delayHook(unsigned dliNotify, PDelayLoadInfo pdli)
{
    switch (dliNotify) {
        case dliStartProcessing :

            // If you want to return control to the helper, return 0.
            // Otherwise, return a pointer to a FARPROC helper function
            // that will be used instead, thereby bypassing the rest
            // of the helper.

            break;

        case dliNotePreLoadLibrary :

            // If you want to return control to the helper, return 0.
            // Otherwise, return your own HMODULE to be used by the
            // helper instead of having it call LoadLibrary itself.

            break;

        case dliNotePreGetProcAddress :

            // If you want to return control to the helper, return 0.
            // If you choose you may supply your own FARPROC function
            // address and bypass the helper's call to GetProcAddress.

            break;

        case dliFailLoadLib :

            // LoadLibrary failed.
            // If you don't want to handle this failure yourself, return 0.
            // In this case the helper will raise an exception
            // (ERROR_MOD_NOT_FOUND) and exit.
            // If you want to handle the failure by loading an alternate
            // DLL (for example), then return the HMODULE for
            // the alternate DLL. The helper will continue execution with
            // this alternate DLL and attempt to find the
            // requested entrypoint via GetProcAddress.

            break;

        case dliFailGetProc :

            // GetProcAddress failed.
            // If you don't want to handle this failure yourself, return 0.
            // In this case the helper will raise an exception
            // (ERROR_PROC_NOT_FOUND) and exit.
            // If you choose, you may handle the failure by returning
            // an alternate FARPROC function address.

            break;

        case dliNoteEndProcessing :

            // This notification is called after all processing is done.
            // There is no opportunity for modifying the helper's behavior
            // at this point except by longjmp()/throw()/RaiseException.
            // No return value is processed.

            break;

        default :

            return NULL;
    }

    return NULL;
}

/*
and then at global scope somewhere:

ExternC const PfnDliHook __pfnDliNotifyHook2 = delayHook;
ExternC const PfnDliHook __pfnDliFailureHook2 = delayHook;
*/
```

## <a name="delay-load-structure-and-constant-definitions"></a><a name="structure-and-constant-definitions"></a> Yük yapısını ve sabit tanımları geciktir

Varsayılan Gecikmeli Yükleme Yardımcısı yordamı, kanca işlevleriyle ve özel durumlar sırasında iletişim kurmak için çeşitli yapılar kullanır. Bu yapılar içinde tanımlanmıştır *`delayimp.h`* . Bu tür makrolar, tür tanımları, bildirim ve hata değerleri, bilgi yapıları ve kanca içine geçilen işaretçiden kanca işlevi türü verilmiştir:

```C
#define _DELAY_IMP_VER  2

#if defined(__cplusplus)
#define ExternC extern "C"
#else
#define ExternC extern
#endif

typedef IMAGE_THUNK_DATA *          PImgThunkData;
typedef const IMAGE_THUNK_DATA *    PCImgThunkData;
typedef DWORD                       RVA;

typedef struct ImgDelayDescr {
    DWORD           grAttrs;        // attributes
    RVA             rvaDLLName;     // RVA to dll name
    RVA             rvaHmod;        // RVA of module handle
    RVA             rvaIAT;         // RVA of the IAT
    RVA             rvaINT;         // RVA of the INT
    RVA             rvaBoundIAT;    // RVA of the optional bound IAT
    RVA             rvaUnloadIAT;   // RVA of optional copy of original IAT
    DWORD           dwTimeStamp;    // 0 if not bound,
                                    // O.W. date/time stamp of DLL bound to (Old BIND)
    } ImgDelayDescr, * PImgDelayDescr;

typedef const ImgDelayDescr *   PCImgDelayDescr;

enum DLAttr {                   // Delay Load Attributes
    dlattrRva = 0x1,                // RVAs are used instead of pointers
                                    // Having this set indicates a VC7.0
                                    // and above delay load descriptor.
    };

//
// Delay load import hook notifications
//
enum {
    dliStartProcessing,             // used to bypass or note helper only
    dliNoteStartProcessing = dliStartProcessing,

    dliNotePreLoadLibrary,          // called just before LoadLibrary, can
                                    //  override w/ new HMODULE return val
    dliNotePreGetProcAddress,       // called just before GetProcAddress, can
                                    //  override w/ new FARPROC return value
    dliFailLoadLib,                 // failed to load library, fix it by
                                    //  returning a valid HMODULE
    dliFailGetProc,                 // failed to get proc address, fix it by
                                    //  returning a valid FARPROC
    dliNoteEndProcessing,           // called after all processing is done, no
                                    //  bypass possible at this point except
                                    //  by longjmp()/throw()/RaiseException.
    };

typedef struct DelayLoadProc {
    BOOL                fImportByName;
    union {
        LPCSTR          szProcName;
        DWORD           dwOrdinal;
        };
    } DelayLoadProc;

typedef struct DelayLoadInfo {
    DWORD               cb;         // size of structure
    PCImgDelayDescr     pidd;       // raw form of data (everything is there)
    FARPROC *           ppfn;       // points to address of function to load
    LPCSTR              szDll;      // name of dll
    DelayLoadProc       dlp;        // name or ordinal of procedure
    HMODULE             hmodCur;    // the hInstance of the library we have loaded
    FARPROC             pfnCur;     // the actual function that will be called
    DWORD               dwLastError;// error received (if an error notification)
    } DelayLoadInfo, * PDelayLoadInfo;

typedef FARPROC (WINAPI *PfnDliHook)(
    unsigned        dliNotify,
    PDelayLoadInfo  pdli
    );
```

## <a name="calculate-necessary-values-for-delay-loading"></a><a name="calculate-necessary-values"></a> Gecikme yüklemesi için gerekli değerleri hesapla

Gecikme Yükleme Yardımcısı yordamının iki kritik bilgi parçasını hesaplaması gerekir. Yardım için, *`delayhlp.cpp`* Bu bilgileri hesaplamak üzere ' de iki satır içi işlev vardır.

- Birincisi, `IndexFromPImgThunkData` geçerli içeri aktarmanın dizinini üç farklı tabloya (içeri aktarma adres tablosu (ıAT), bağlı içeri aktarma adresi tablosu (BIAT) ve ilişkisiz içeri aktarma adres tablosu (UıAT)) hesaplar.

- İkincisi, `CountOfImports` geçerli BIR ıAT içindeki içeri aktarma sayısını sayar.

```C
// utility function for calculating the index of the current import
// for all the tables (INT, BIAT, UIAT, and IAT).
__inline unsigned
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {
    return pitdCur - pitdBase;
    }

// utility function for calculating the count of imports given the base
// of the IAT. NB: this only works on a valid IAT!
__inline unsigned
CountOfImports(PCImgThunkData pitdBase) {
    unsigned        cRet = 0;
    PCImgThunkData  pitd = pitdBase;
    while (pitd->u1.Function) {
        pitd++;
        cRet++;
        }
    return cRet;
    }
```

## <a name="support-unload-of-a-delay-loaded-dll"></a><a name="unload-a-delay-loaded-dll"></a> Gecikmeli yüklenen DLL 'nin yüklemesini destekler

Gecikmeli yüklenen DLL yüklendiğinde, varsayılan Gecikmeli Yükleme Yardımcısı, gecikme yükleme tanımlayıcılarının bir işaretçiye sahip olup olmadığını ve alanda orijinal içeri aktarma adresi tablosunun (ıAT) bir kopyasına sahip olup olmadığını denetler `pUnloadIAT` . Bu durumda, yardımcı, bir listedeki işaretçiyi içeri aktarma gecikmesi tanımlayıcısına kaydeder. Bu giriş, yardımcı işlevin dll 'yi ada göre bulmasını sağlar ve bu DLL 'yi açıkça kaldırmayı destekler.

Bir Gecikmeli yüklenen DLL 'yi açıkça kaldırma ile ilgili yapılar ve işlevler aşağıda verilmiştir:

```cpp
//
// Unload support from delayimp.h
//

// routine definition; takes a pointer to a name to unload

ExternC
BOOL WINAPI
__FUnloadDelayLoadedDLL2(LPCSTR szDll);

// structure definitions for the list of unload records
typedef struct UnloadInfo * PUnloadInfo;
typedef struct UnloadInfo {
    PUnloadInfo     puiNext;
    PCImgDelayDescr pidd;
    } UnloadInfo;

// from delayhlp.cpp
// the default delay load helper places the unloadinfo records in the
// list headed by the following pointer.
ExternC
PUnloadInfo __puiHead;
```

`UnloadInfo`Yapı, `LocalAlloc` sırasıyla ve gibi uygulamalar kullanan bir C++ sınıfı kullanılarak uygulanır `LocalFree` `operator new` `operator delete` . Bu seçenekler, listenin başı olarak kullanılan standart bağlantılı bir listede tutulur `__puiHead` .

`__FUnloadDelayLoadedDLL`' İ çağırdığınızda, yüklenen dll 'ler listesinde sağladığınız adı bulmaya çalışır. (Tam eşleşme gereklidir.) Bulunursa, içindeki ıAT 'nin kopyası, `pUnloadIAT` dönüştürücü işaretçilerini geri yüklemek için çalışan IAT 'nin üstüne kopyalanır. Ardından, kitaplık kullanılarak serbest bırakılır `FreeLibrary` , eşleşen `UnloadInfo` kaydın listede bağlantısı kaldırılır ve silinir ve `TRUE` döndürülür.

İşlevin bağımsız değişkeni `__FUnloadDelayLoadedDLL2` büyük/küçük harfe duyarlıdır. Örneğin şunu belirtmeniz gerekir:

```cpp
__FUnloadDelayLoadedDLL2("user32.dll");
```

değil:

```cpp
__FUnloadDelayLoadedDLL2("User32.DLL");
```

Gecikmeli yüklenen DLL 'yi kaldırma örneği için bkz. [Gecikmeli yüklenen dll 'ı açıkça kaldırma](linker-support-for-delay-loaded-dlls.md).

## <a name="develop-your-own-delay-load-helper-function"></a><a name="develop-your-own-helper-function"></a> Kendi gecikme yük Yardımcısı işlevinizi geliştirme

Gecikme yükü Yardımcısı yordamının kendi sürümünüzü sağlamak isteyebilirsiniz. Kendi yordamınıza, DLL veya içeri aktarmalar adına göre belirli işlemleri yapabilirsiniz. Kendi kodunuzu eklemenin iki yolu vardır: kendi yardımcı işlevinizi, büyük olasılıkla sağlanan koda göre kodlayın. Ya da, [bildirim kancalarını](error-handling-and-notification.md#notification-hooks)kullanarak kendi işlevinizi çağırmak için sağlanan yardımcıyı kanca.

### <a name="code-your-own-helper"></a>Kendi yardımcınızın kodunu yapın

Kendi yardımcı yordamınızın oluşturulması basittir. Mevcut kodu, yeni işleviniz için bir kılavuz olarak kullanabilirsiniz. İşlevinizin mevcut yardımcı ile aynı çağırma kurallarını kullanması gerekir. Ve bağlayıcı tarafından oluşturulan dönüştürücüler döndürürse, uygun bir işlev işaretçisi döndürmelidir. Kodunuzu oluşturduktan sonra, aramayı karşıya da çağrmış olabilirsiniz.

### <a name="use-the-start-processing-notification-hook"></a>İşlemi Başlat bildirim kancasını kullan

Bildirimin varsayılan Yardımcısı ile aynı değerleri alan Kullanıcı tarafından sağlanan bir bildirim kanca işlevine yeni bir işaretçi sağlamak büyük olasılıkla en kolay yoldur `dliStartProcessing` . Bu noktada, varsayılan yardımcıya başarılı bir geri dönme varsayılan yardımdaki tüm diğer işlemleri atladığı için kanca işlevi aslında yeni yardımcı işlev haline gelebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli yüklenen DLL'ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md#explicitly-unload-a-delay-loaded-dll)
