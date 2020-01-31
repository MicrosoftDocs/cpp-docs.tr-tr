---
title: Bir yürütülebilir dosyayı DLL’ye bağlama
ms.date: 08/22/2019
helpviewer_keywords:
- run time [C++], linking
- dynamic load linking [C++]
- linking [C++], DLLs
- DLLs [C++], linking
- implicit linking [C++]
- explicit linking [C++]
- executable files [C++], linking to DLLs
- loading DLLs [C++]
ms.assetid: 7592e276-dd6e-4a74-90c8-e1ee35598ea3
ms.openlocfilehash: 2f907fedcaaf9897749ee0eb6a7ea5a33e1af679
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821388"
---
# <a name="link-an-executable-to-a-dll"></a>Bir yürütülebilir dosyayı DLL’ye bağlama

Yürütülebilir dosya, bir DLL 'yi iki şekilde bağlar (veya yükler):

- İşletim sisteminin DLL 'yi kullanan yürütülebilir dosya ile aynı anda yüklediği *örtük bağlama*. İstemci yürütülebilir dosyası, DLL 'nin içe aktarılmış işlevlerini, işlevlerin statik olarak bağlanıp çalıştırılabilir dosya içinde bulunduğu şekilde çağırır. Örtük bağlama bazen *statik yükleme* veya *yükleme zamanı dinamik bağlama*olarak adlandırılır.

- İşletim sisteminin, çalışma zamanında DLL 'yi isteğe bağlı olarak yüklediği *Açık bağlama*. Açık bağlama tarafından DLL kullanan bir yürütülebilir dosya, DLL 'yi açıkça yükleyip bellekten kaldırmanız gerekir. Ayrıca, DLL 'den kullandığı her işleve erişmek için bir işlev işaretçisi de ayarlaması gerekir. Statik olarak bağlı bir kitaplıktaki işlevlere veya örtük olarak bağlı bir DLL 'ye yapılan çağrıların aksine, istemci yürütülebilir dosyası işlev işaretçileri aracılığıyla açıkça bağlanmış bir DLL 'de içe aktarılmış işlevleri çağırmalıdır. Açık bağlama bazen *dinamik yük* veya *çalışma zamanı dinamik bağlama*olarak adlandırılır.

Yürütülebilir dosya, aynı DLL 'ye bağlanmak için bağlama yöntemini kullanabilir. Ayrıca, bu yöntemler birbirini dışlamamalıdır; bir yürütülebilir dosya örtük olarak bir DLL 'ye bağlantı oluşturabilir ve başka bir şekilde buna açıkça eklenebilir.

<a name="determining-which-linking-method-to-use"></a>

## <a name="determine-which-linking-method-to-use"></a>Hangi bağlama yönteminin kullanılacağını belirleme

Örtük bağlama veya açık bağlama kullanılması gerekip gerekmediğini uygulamanız için yapmanız gereken bir mimari karardır. Her yöntemin avantajları ve dezavantajları vardır.

### <a name="implicit-linking"></a>Örtük bağlama

Örtük bağlama, bir uygulamanın kodu, bir, bir bir DLL işlevi çağırdığında oluşur. Çağıran yürütülebilir dosya için kaynak kodu derlendiğinde veya birleştirildiğinde, DLL işlevi çağrısı nesne kodunda bir dış işlev başvurusu oluşturur. Bu dış başvuruyu çözümlemek için, uygulamanın, DLL üreticisi tarafından belirtilen içeri aktarma kitaplığıyla (. lib dosyası) bağlanması gerekir.

İçeri aktarma kitaplığı yalnızca DLL 'yi yüklemek ve DLL 'deki işlevlere çağrıları uygulamak için kod içerir. İçeri aktarma kitaplığındaki bir dış işlevin bulunması, bağlayıcının bu işlev için kodun bir DLL içinde olduğunu bildirir. Dll 'Lerin dış başvurularını çözümlemek için bağlayıcı, sisteme, işlem başladığında DLL kodunu nerede bulacağını belirten yürütülebilir dosyaya bilgi ekler.

Sistem dinamik bağlantılı başvurular içeren bir programı başlattığında, gerekli dll 'Leri bulmak için programın yürütülebilir dosyasındaki bilgileri kullanır. DLL 'yi bulamazsa, sistem işlemi sonlandırır ve hatayı raporlayan bir iletişim kutusu görüntüler. Aksi halde sistem, DLL modüllerini işlem adres alanıyla eşler.

Dll 'Lerden herhangi birinde `DllMain`gibi başlatma ve sonlandırma kodu için bir giriş noktası işlevi varsa, işletim sistemi işlevini çağırır. Giriş noktası işlevine geçirilen parametrelerden biri, DLL 'nin işleme ilişdiğini belirten bir kodu belirtir. Giriş noktası işlevi TRUE döndürmezse, sistem işlemi sonlandırır ve hatayı raporlar.

Son olarak, sistem, DLL işlevleri için başlangıç adreslerini sağlamak üzere işlemin yürütülebilir kodunu değiştirir.

Programın kodunun geri kalanı gibi yükleyici, işlem başladığında DLL kodunu işlemin adres alanına eşler. İşletim sistemi bu dosyayı yalnızca gerektiğinde belleğe yükler. Sonuç olarak, Windows 'un önceki sürümlerinde yüklemeyi denetlemek için. def dosyaları tarafından kullanılan `PRELOAD` ve `LOADONCALL` kodu özniteliklerinin artık anlamı yoktur.

### <a name="explicit-linking"></a>Açık bağlama

Çoğu uygulama, kullanmak için en kolay bağlama yöntemi olduğundan örtük bağlama kullanır. Ancak, Açık bağlama gereken durumlar da vardır. Açık bağlama kullanmanın bazı yaygın nedenleri aşağıda verilmiştir:

- Uygulama, çalışma zamanına kadar yüklediği DLL 'nin adını bilmez. Örneğin, uygulama DLL adını ve başlangıç olarak bir yapılandırma dosyasından aktarılmış işlevleri alabilir.

- İşlem başlangıcında DLL bulunamazsa, örtük bağlama kullanan bir işlem işletim sistemi tarafından sonlandırılır. Açık bağlama kullanan bir işlem bu durumda sonlandırılmaz ve hatadan kurtarmayı deneyebilir. Örneğin, işlem hatayı kullanıcıya bildirebilir ve kullanıcının DLL 'ye başka bir yol belirtmesini sağlayabilir.

- Dolaylı bağlama kullanan bir işlem, bağlı olduğu dll 'Lerden herhangi biri başarısız olan bir `DllMain` işlevine sahip olursa da sonlandırılır. Açık bağlama kullanan bir işlem bu durumda sonlandırılmadı.

- Windows, uygulama yüklendiğinde tüm dll 'Leri yüklediği için, birden çok dll 'ye örtülü olarak bağlanan bir uygulama başlatılabilir. Bir uygulama, başlangıç performansını artırmak için yalnızca yüklemeden hemen sonra gerekli olan DLL 'Ler için örtülü bağlamayı kullanabilir. Yalnızca gerektiğinde diğer dll 'Leri yüklemek için açık bağlamayı kullanabilir.

- Açık bağlama, bir içeri aktarma kitaplığı kullanarak uygulamayı bağlama gereksinimini ortadan kaldırır. DLL 'deki değişiklikler dışa aktarma sıra sayıclarından oluşmasına neden olursa, bir işlevin adını kullanarak `GetProcAddress` ve bir sıra değeri değil, uygulamaların yeniden bağlanmak zorunda kalmaz. Örtük bağlama kullanan uygulamalar yine de değiştirilen içeri aktarma kitaplığına yeniden bağlanmalıdır.

Aşağıda, Açık bağlama konusunda bilinmesi için iki tehlikeli yer verilmiştir:

- DLL 'nin bir `DllMain` giriş noktası işlevi varsa, işletim sistemi, işlevi `LoadLibrary`çağıran iş parçacığının bağlamında çağırır. Daha önce, `FreeLibrary` işlevine karşılık gelen bir çağrısı olmayan `LoadLibrary` için önceki bir çağrı nedeniyle, DLL zaten işleme eklenmişse, giriş noktası işlevi çağrılmaz. DLL, bir işlemin her iş parçacığını başlatmak için bir `DllMain` işlevi kullanıyorsa açık bağlama sorunlara yol açabilir çünkü `LoadLibrary` (veya `AfxLoadLibrary`) çağrıldığında zaten var olan herhangi bir iş parçacığı başlatılmaz.

- Bir DLL, `__declspec(thread)`olarak statik kapsam verileri bildiriyorsa, açıkça bağlanmışsa koruma hatasına neden olabilir. DLL bir `LoadLibrary`çağrısıyla yüklendikten sonra, kod bu verilere başvurduğunda bir koruma hatasına neden olur. (Statik kapsam verileri hem genel hem de yerel statik öğeleri içerir.) Bu nedenle, bir DLL oluşturduğunuzda, iş parçacığı yerel depolama kullanmaktan kaçının. Bunu yapmak için, dll kullanıcılarınızı, DLL 'nizi dinamik olarak yükleme olasılığı hakkında bilgilendirin. Daha fazla bilgi için bkz. [dinamik bağlantı kitaplığında iş parçacığı yerel depolama alanı kullanma (Windows SDK)](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library).

<a name="linking-implicitly"></a>

## <a name="how-to-use-implicit-linking"></a>Örtük bağlama kullanma

Bir DLL 'yi örtük bağlama ile kullanmak için, istemci yürütülebilir dosyalarının bu dosyaları DLL sağlayıcısından alması gerekir:

- DLL 'de, yayımlanan verilerin, işlevlerin ve C++ sınıfların bildirimlerini içeren bir veya daha fazla üst bilgi dosyası (. h dosyası). DLL tarafından dışarıya alınan sınıfların, işlevlerin ve verilerin tümü başlık dosyasında `__declspec(dllimport)` işaretlenmelidir. Daha fazla bilgi için bkz. [dllexport, dllimport](../cpp/dllexport-dllimport.md).

- Yürütülebilire bağlanacak bir içeri aktarma kitaplığı. Bağlayıcı, DLL yapılandırıldığında içeri aktarma kitaplığını oluşturur. Daha fazla bilgi için bkz. [LIB Files as bağlayıcı girişi](reference/dot-lib-files-as-linker-input.md).

- Gerçek DLL dosyası.

Örtük bağlama yoluyla bir DLL 'deki verileri, işlevleri ve sınıfları kullanmak için, tüm istemci kaynak dosyaları bunları bildiren üst bilgi dosyalarını içermelidir. Kodlama perspektifinden, dışarıya aktarılmış işlevlere yapılan çağrılar tıpkı diğer işlev çağrıları gibi.

İstemci yürütülebilir dosyasını oluşturmak için DLL 'nin içeri aktarma kitaplığıyla bağlantı oluşturmanız gerekir. Dış derleme görevleri dosyası veya yapı sistemi kullanıyorsanız, içeri aktarma kitaplığını, diğer nesne dosyalarıyla veya bağlantı yaptığınız kitaplıklarla birlikte belirtin.

İşletim sisteminin, çağıran yürütülebilir dosyayı yüklediğinde DLL dosyasını bulabilmeleri gerekir. Bu, uygulamanızı yüklerken DLL 'nin varlığını dağıtmanız veya doğrulamanız gereken anlamına gelir.

<a name="linking-explicitly"></a>

## <a name="how-to-link-explicitly-to-a-dll"></a>Bir DLL 'ye açıkça bağlantı oluşturma

Bir DLL 'yi açık bağlama ile kullanmak için, uygulamaların çalışma zamanında DLL 'yi açıkça yüklemesi için bir işlev çağrısı yapması gerekir. Bir DLL 'ye açıkça bağlantı sağlamak için bir uygulamanın şunları yapmanız gerekir:

- DLL 'yi yüklemek ve bir modül tanıtıcısı almak için [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) veya benzer bir işlev çağırın.

- Uygulamanın çağırdığı her bir içe aktarılmış işleve bir işlev işaretçisi almak için [GetProcAddress](getprocaddress.md) çağrısı yapın. Uygulamalar, DLL işlevlerini bir işaretçi aracılığıyla çağırdığından, derleyici dış başvuru oluşturmaz, bu nedenle içeri aktarma kitaplığıyla bağlantı oluşturmanız gerekmez. Ancak, çağrmış olan işlevlerin çağrı imzasını tanımlayan bir `typedef` veya `using` deyiminiz olmalıdır.

- DLL ile işiniz bittiğinde [FreeLibrary](freelibrary-and-afxfreelibrary.md) ' i çağırın.

Örneğin, bu örnek işlev, "MyDLL" adlı bir DLL yüklemek için `LoadLibrary` çağırır, "DLLFunc1" adlı bir işleve işaretçi almak için `GetProcAddress` çağırır, işlevi çağırır ve sonucu kaydeder ve sonra DLL 'yi kaldırmak için `FreeLibrary` çağırır.

```C
#include "windows.h"

typedef HRESULT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT*);

HRESULT LoadAndCallSomeFunction(DWORD dwParam1, UINT * puParam2)
{
    HINSTANCE hDLL;               // Handle to DLL
    LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer
    HRESULT hrReturnVal;

    hDLL = LoadLibrary("MyDLL");
    if (NULL != hDLL)
    {
        lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL, "DLLFunc1");
        if (NULL != lpfnDllFunc1)
        {
            // call the function
            hrReturnVal = lpfnDllFunc1(dwParam1, puParam2);
        }
        else
        {
            // report the error
            hrReturnVal = ERROR_DELAY_LOAD_FAILED;
        }
        FreeLibrary(hDLL);
    }
    else
    {
        hrReturnVal = ERROR_DELAY_LOAD_FAILED;
    }
    return hrReturnVal;
}
```

Bu örneğin aksine, çoğu durumda, belirli bir DLL için uygulamanızda yalnızca bir kez `LoadLibrary` ve `FreeLibrary` çağırmanız gerekir. DLL 'de birden çok işlev çağıracaksanız veya DLL işlevlerini tekrar tekrar çağırdığınızda bu durum özellikle doğrudur.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [İçeri Aktarma Kitaplıkları ve Dışarı Aktarma Dosyalarıyla Çalışma](reference/working-with-import-libraries-and-export-files.md)

- [Dinamik bağlantı kitaplığı arama sırası](/windows/win32/Dlls/dynamic-link-library-search-order)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'daC++ C/dll oluşturma](dlls-in-visual-cpp.md)
