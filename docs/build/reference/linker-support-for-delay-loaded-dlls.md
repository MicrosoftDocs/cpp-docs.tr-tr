---
description: "Daha fazla bilgi edinin: Gecikmeli yüklenen dll 'Ler için bağlayıcı desteği"
title: Gecikmeli yüklenen DLL'ler için bağlayıcı desteği
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.openlocfilehash: 02991d6ac409ef301e326eea63ece8c5c7775010
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522423"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Gecikmeli yüklenen DLL'ler için bağlayıcı desteği

MSVC Bağlayıcısı, dll 'lerin gecikmeli yüklenmesini destekler. Bu özellik, Windows SDK işlevlerini kullanma [`LoadLibrary`](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) ve [`GetProcAddress`](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) DLL gecikmeli yüklemeyi uygulama ihtiyacını sizi maliyetinden kurtarır.

Gecikmeli yük olmadan, çalışma zamanında DLL yüklemek için tek yol, `LoadLibrary` ve ' ı kullanmaktır `GetProcAddress` ; işletim sistemi, bu dosyayı kullanan ÇALıŞTıRıLABILIR veya DLL yüklendiğinde dll 'yi yükler.

Gecikmeli yük ile, bir DLL 'yi örtük olarak bağladığınızda bağlayıcı, program bu DLL 'de bir işlev çağırana kadar DLL yükünü geciktirmek için seçenekler sağlar.

Bir uygulama, bir yardımcı işlevle [ `/DELAYLOAD` (yük içeri aktarmayı geciktir)](delayload-delay-load-import.md) BAĞLAYıCı seçeneğini kullanarak dll yüklemeyi geciktirebilirler. (Varsayılan bir yardımcı işlev uygulamasını Microsoft tarafından sağlanır.) Yardımcı işlevi, ve ' i çağırarak çalışma zamanında DLL 'yi isteğe bağlı olarak yükler `LoadLibrary` `GetProcAddress` .

Şu durumlarda bir DLL yükleme gecikmesini göz önünde bulundurun:

- Programınız DLL 'de bir işlev çağırmayabilir.

- DLL 'deki bir işlev, programınızın yürütülmesine geç kadar çağrılamaz.

Bir DLL 'nin geciken yüklemesi, bir EXE veya DLL projesinin oluşturulması sırasında belirtilebilir. Bir veya daha fazla dll 'nin kendisini yüklemeyi geciktireeden bir DLL projesi içinde Gecikmeli yüklenen bir giriş noktası çağırmamalıdır `DllMain` .

## <a name="specify-dlls-to-delay-load"></a><a name="specify-dlls-to-delay-load"></a> Yük gecikmesi için dll 'Leri belirtin

Hangi dll 'Lerin yük, bağlayıcı seçeneğini kullanarak geciktirimesini belirtebilirsiniz [`/delayload:`*`dllname`*](delayload-delay-load-import.md) . Kendi yardımcı işlevinizin sürümünü kullanmayı planlamıyorsanız, programınızı *`delayimp.lib`* (masaüstü uygulamaları için) veya *`dloadhelper.lib`* (UWP uygulamaları için) ile bağlamanız gerekir.

Bir DLL yükleme gecikmesi için basit bir örnek aşağıda verilmiştir:

```cpp
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll
#include <windows.h>
// uncomment these lines to remove .libs from command line
// #pragma comment(lib, "delayimp")
// #pragma comment(lib, "user32")

int main() {
   // user32.dll will load at this point
   MessageBox(NULL, "Hello", "Hello", MB_OK);
}
```

Projenin hata ayıklama sürümünü oluşturun. Hata ayıklayıcıyı kullanarak kodda adım adım ilerleyin ve *`user32.dll`* yalnızca çağrısını yaptığınızda yüklendiğini görürsünüz `MessageBox` .

## <a name="explicitly-unload-a-delay-loaded-dll"></a><a name="explicitly-unload-a-delay-loaded-dll"></a> Gecikmeli yüklenen DLL 'i açıkça kaldırma

[`/delay:unload`](delay-delay-load-import-settings.md)Bağlayıcı seçeneği, kodunuzun, Gecikmeli yüklenen BIR DLL 'yi açıkça kaldırmasına izin verir. Varsayılan olarak, Gecikmeli yüklenen içeri aktarmalar içeri aktarma adresi tablosunda (ıAT) kalır. Ancak, **`/delay:unload`** bağlayıcı komut satırında kullanırsanız, yardımcı işlevi, dll 'nin açıkça kaldırılmasını bir çağrı ile destekler `__FUnloadDelayLoadedDLL2` ve IAT 'yi özgün biçimine sıfırlar. Şimdi geçersiz işaretçiler üzerine yazılır. IAT, bir, varsa [`ImgDelayDescr`](understanding-the-helper-function.md#calling-conventions-parameters-and-return-type) orijinal IAT öğesinin bir kopyasının adresini içeren bir alandır.

### <a name="example-of-unloading-a-delay-loaded-dll"></a>Gecikmeli yüklenen DLL 'yi kaldırma örneği

Bu örnekte, bir işlevi içeren bir DLL 'nin açıkça nasıl *`MyDll.dll`* kaldırabileceği gösterilmektedir `fnMyDll` :

```C
// link with /link /DELAYLOAD:MyDLL.dll /DELAY:UNLOAD
#include <windows.h>
#include <delayimp.h>
#include "MyDll.h"
#include <stdio.h>

#pragma comment(lib, "delayimp")
#pragma comment(lib, "MyDll")
int main()
{
    BOOL TestReturn;
    // MyDLL.DLL will load at this point
    fnMyDll();

    //MyDLL.dll will unload at this point
    TestReturn = __FUnloadDelayLoadedDLL2("MyDll.dll");

    if (TestReturn)
        printf_s("\nDLL was unloaded");
    else
        printf_s("\nDLL was not unloaded");
}
```

Gecikmeli yüklenen DLL 'yi kaldırma hakkında önemli notlar:

- `__FUnloadDelayLoadedDLL2`İşlevin uygulamasını *`delayhlp.cpp`* , MSVC dizininde, dosyasında bulabilirsiniz *`include`* . Daha fazla bilgi için bkz. [gecikme Yükleme Yardımcısı Işlevini anlama](understanding-the-helper-function.md).

- *`name`* İşlevin parametresi, `__FUnloadDelayLoadedDLL2` içeri aktarma kitaplığı 'nın içerdiği, tam olarak eşleşmelidir (örneğin, büyük/küçük harf). (Bu dize görüntüdeki içeri aktarma tablosunda da bulunur.) Kullanarak içeri aktarma kitaplığının içeriğini görüntüleyebilirsiniz [`DUMPBIN /DEPENDENTS`](dependents.md) . Büyük/küçük harfe duyarsız bir dize eşleşmesi tercih ediyorsanız, `__FUnloadDelayLoadedDLL2` büyük/küçük harfe DUYARSıZ CRT dize işlevlerinden birini veya bir WINDOWS API çağrısını kullanmak için ' yi güncelleştirebilirsiniz.

## <a name="bind-delay-loaded-imports"></a><a name="bind-delay-loaded-imports"></a> Gecikmeli yüklenen içeri aktarmaları bağlama

Varsayılan bağlayıcı davranışı, Gecikmeli yüklenen DLL için bağlanabilir bir içeri aktarma adresi tablosu (ıAT) oluşturmaktır. DLL bağlı ise, yardımcı işlevi, `GetProcAddress` başvurulan her içeri aktarmaların her birine çağırmak yerine bağlı bilgileri kullanmayı dener. Zaman damgası ya da tercih edilen adres yüklenen DLL 'nin ile eşleşmezse, yardımcı işlevi, bağlantılı içeri aktarma adresi tablosunun güncel olmadığını varsayar. IAT yok gibi devam eder.

Bir DLL 'nin Gecikmeli yüklenen içeri aktarmalarını bağlamayı hiç belirtmediğiniz takdirde [`/delay:nobind`](delay-delay-load-import-settings.md) bağlayıcı komut satırında öğesini belirtin. Bağlayıcı, görüntü dosyasına alan kaydeden, bağlantılı içeri aktarma adresi tablosunu oluşturmaz.

## <a name="load-all-imports-for-a-delay-loaded-dll"></a><a name="load-all-imports-for-a-delay-loaded-dll"></a> Gecikmeli yüklenen DLL için tüm içeri aktarmaları yükle

`__HrLoadAllImportsForDll`İçinde tanımlanan işlevi, *`delayhlp.cpp`* bağlayıcının bağlayıcı seçeneğiyle BELIRTILEN bir dll 'den tüm içeri aktarmaları yüklemesini söyler [`/delayload`](delayload-delay-load-import.md) .

Tüm içeri aktarmaları aynı anda yüklediğinizde, hata işlemeyi tek bir yerde merkezi hale getirebilirsiniz. İçeri aktarmalar için yapılan tüm gerçek çağrılar etrafında yapılandırılmış özel durum işlemenin önüne geçabilirsiniz. Ayrıca, uygulamanızın bir işlem aracılığıyla hata vererek başarısız olduğu bir durumu önler: Örneğin, yardımcı kod, bir içeri aktarma işlemini başarıyla yükledikten sonra, bir içeri aktarma işlemi başarısız olursa.

Çağırma `__HrLoadAllImportsForDll` , kancalar ve hata işleme davranışlarını değiştirmez. Daha fazla bilgi için bkz. [hata işleme ve bildirim](error-handling-and-notification.md).

`__HrLoadAllImportsForDll` DLL içinde depolanan ada büyük küçük harfe duyarlı bir karşılaştırma yapar.

`__HrLoadAllImportsForDll` `TryDelayLoadAllImports` Adlandırılmış bir dll yüklemeyi denemek için adlı bir işlevde kullanılan bir örnek aşağıda verilmiştir. `CheckDelayException`Özel durum davranışını anlamak için bir işlevi kullanır.

```C
int CheckDelayException(int exception_value)
{
    if (exception_value == VcppException(ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) ||
        exception_value == VcppException(ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND))
    {
        // This example just executes the handler.
        return EXCEPTION_EXECUTE_HANDLER;
    }
    // Don't attempt to handle other errors
    return EXCEPTION_CONTINUE_SEARCH;
}

bool TryDelayLoadAllImports(LPCSTR szDll)
{
    __try
    {
        HRESULT hr = __HrLoadAllImportsForDll(szDll);
        if (FAILED(hr))
        {
            // printf_s("Failed to delay load functions from %s\n", szDll);
            return false;
        }
    }
    __except (CheckDelayException(GetExceptionCode()))
    {
        // printf_s("Delay load exception for %s\n", szDll);
        return false;
    }
    // printf_s("Delay load completed for %s\n", szDll);
    return true;
}
```

Sonucunu, `TryDelayLoadAllImports` içeri aktarma işlevlerini çağırıp çağırmayacağını denetlemek için kullanabilirsiniz.

## <a name="error-handling-and-notification"></a>Hata işleme ve bildirme

Programınız Gecikmeli yüklenen dll 'Ler kullanıyorsa, robustly hatalarının işlenmesi gerekir. Program çalışırken meydana gelen arızalar işlenmeyen özel durumlara neden olur. DLL gecikmesi yükleme hatası işleme ve bildirimi hakkında daha fazla bilgi için bkz. [hata işleme ve bildirim](error-handling-and-notification.md).

## <a name="dump-delay-loaded-imports"></a><a name="dump-delay-loaded-imports"></a> Gecikmeli yüklenen içeri aktarmalar dökümünü al

Gecikmeli yüklenen içeri aktarmalar kullanılarak dökülebilir [`DUMPBIN /IMPORTS`](imports-dumpbin.md) . Bu içeri aktarmalar, standart içeri aktarımlara göre biraz farklı bilgilerle gösterilir. Bunlar, listenin kendi bölümlerine bölünmüştür `/imports` ve açıkça Gecikmeli yüklenen içeri aktarmalar olarak etiketlendirilir. Görüntüde bir kaldırma bilgisi varsa, bu belirtilir. Bağlama bilgileri varsa, hedef DLL 'nin saat ve tarih damgası içeri aktarmaların bağlı adresleriyle birlikte belirtilir.

## <a name="constraints-on-delay-load-dlls"></a><a name="constraints-on-delay-load-dlls"></a> Gecikmeli yükleme dll 'Lerinde kısıtlamalar

DLL içeri aktarımlarının gecikme yüklemesinde çeşitli kısıtlamalar vardır.

- Verilerin içeri aktarmaları desteklenmez. Geçici bir çözüm, `LoadLibrary` (veya [`GetModuleHandle`](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulehandlew) gecikme Yükleme Yardımcısı 'nın dll 'yi yükledikten sonra kullanarak) verileri doğrudan içeri aktarmayı açıkça işleymaktır `GetProcAddress` .

- Yükleme gecikmesi *`Kernel32.dll`* desteklenmez. Bu DLL 'nin çalışması gecikmeli yük Yardımcısı yordamları için yüklenmelidir.

- İletilen giriş noktalarının [bağlanması](#bind-delay-loaded-imports) desteklenmez.

- Bir işlem, bir DLL gecikmeli yüklenmişse, başlatma sırasında yüklenmeden farklı davranış gösterebilir. Gecikmeli yüklenen DLL 'nin giriş noktasında gerçekleşen işlem başına başlatmalar varsa bu durum görülebilir. Diğer durumlarda, kullanılarak belirtilen statik TLS (iş parçacığı yerel depolaması), [`__declspec(thread)`](../../cpp/thread.md) Ile dll ile yüklendiğinde işlenmez `LoadLibrary` . ,,, Ve kullanan dinamik TLS, [`TlsAlloc`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) [`TlsFree`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsfree) [`TlsGetValue`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) [`TlsSetValue`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlssetvalue) statik veya Gecikmeli yüklenen dll 'lerde kullanılmaya devam etmektedir.

- Her bir işlevin ilk çağrısından sonra içeri aktarılan işlevlere statik genel işlev işaretçilerini yeniden başlatın. Bu gereklidir çünkü bir işlev işaretçisinin ilk kullanımı, yüklü işlevi değil dönüştürücü için işaret ediyor.

- Şu anda, normal içeri aktarma mekanizmasını kullanırken bir DLL 'den yalnızca belirli yordamları yüklemeyi geciktirmenin bir yolu yoktur.

- Özel çağırma kuralları (x86 mimarilerinde koşul kodlarını kullanma gibi) desteklenmez. Ayrıca, kayan nokta kayıtları herhangi bir platformda kaydedilmez. Özel yardımcı yordamınız veya kanca yordamlarınız kayan nokta türleri kullanıyorsa dikkatli olmak: yordamlar, çağırma kurallarını kayan nokta parametreleriyle kaydet kullanan makinelerde tam kayan nokta durumunu kaydedip geri yüklemesi gerekir. Özellikle, yardım işlevindeki bir sayısal veri işlemcisi (NDP) yığınında kayan nokta parametreleri alan CRT işlevleri çağırırsanız, CRT DLL 'nin Gecikmeli yükleme konusunda dikkatli olun.

## <a name="understand-the-delay-load-helper-function"></a>Gecikme yükleme yardımcısı işlevini anlayın

Bağlayıcı için yardımcı işlev-desteklenen Gecikmeli yükleme, çalışma zamanında DLL 'yi gerçekten yükler. Davranışını özelleştirmek için yardımcı işlevini değiştirebilirsiniz. İçinde sağlanan yardımcı işlevini kullanmak yerine *`delayimp.lib`* kendi işlevinizi yazın ve programınıza bağlayın. Bir yardımcı işlev, tüm Gecikmeli yüklenen dll 'Leri sunar. Daha fazla bilgi için bkz. [gecikme Yükleme Yardımcısı Işlevini anlama](understanding-the-helper-function.md) ve [kendi yardımcı işlevinizi geliştirme](understanding-the-helper-function.md#develop-your-own-helper-function).

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](../dlls-in-visual-cpp.md)<br/>
[MSVC bağlayıcı başvurusu](linking.md)
