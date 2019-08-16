---
title: Bir yürütülebilir dosyayı DLL’ye bağlama
ms.date: 11/04/2016
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
ms.openlocfilehash: c4f9ea7a3606612189e85401b75a0577896fd90e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493220"
---
# <a name="link-an-executable-to-a-dll"></a>Bir yürütülebilir dosyayı DLL’ye bağlama

Yürütülebilir dosya, bir DLL 'yi iki şekilde bağlar (veya yükler):

- İşletim sisteminin, kullanan çalıştırılabilir dosya yüklendiğinde DLL 'yi yüklediği *örtük bağlama*. İstemci yürütülebilir dosyası, işlevlerin statik olarak bağlanıp çalıştırılabilir dosya içinde bulunduğu gibi, DLL 'nin içe aktarılmış işlevlerini çağırır. Örtük bağlama bazen *statik yükleme* veya *yükleme zamanı dinamik bağlama*olarak adlandırılır.

- İşletim sisteminin, çalışma zamanında DLL 'yi isteğe bağlı olarak yüklediği *Açık bağlama*. Açık bağlama tarafından DLL kullanan bir yürütülebilir dosya, DLL 'yi açık bir şekilde yüklemek ve kaldırmak ve DLL tarafından yayımlanan işlevlere erişmek için işlev çağrıları yapmanız gerekir. Statik olarak bağlı bir kitaplıktaki işlevlere yapılan çağrıların aksine, istemci yürütülebilir dosyası bir DLL 'deki bir işlev işaretçisi aracılığıyla bir DLL içindeki aktarılmış işlevleri çağırmalıdır. Açık bağlama bazen *dinamik yük* veya *çalışma zamanı dinamik bağlama*olarak adlandırılır.

Yürütülebilir dosya, aynı DLL 'ye bağlanmak için bağlama yöntemini kullanabilir. Ayrıca, bu yöntemler birbirini dışlamamalıdır; bir yürütülebilir dosya bir DLL 'ye örtük olarak bağlanabilir ve diğeri buna açıkça eklenebilir.

<a name="determining-which-linking-method-to-use"></a>

## <a name="link-an-executable-to-a-dll"></a>Bir yürütülebilir dosyayı DLL’ye bağlama

Örtük bağlama veya açık bağlama kullanılması gerekip gerekmediğini uygulamanız için yapmanız gereken bir mimari karardır. Her yöntemin avantajları ve dezavantajları vardır.

### <a name="implicit-linking"></a>Örtük bağlama

Örtük bağlama, bir uygulamanın kodu, bir, bir bir DLL işlevi çağırdığında oluşur. Çağıran yürütülebilir dosya için kaynak kodu derlendiğinde veya birleştirildiğinde, DLL işlevi çağrısı nesne kodunda bir dış işlev başvurusu oluşturur. Bu dış başvuruyu çözümlemek için, uygulamanın, DLL üreticisi tarafından belirtilen içeri aktarma kitaplığıyla (. lib dosyası) bağlanması gerekir.

İçeri aktarma kitaplığı yalnızca DLL 'yi yüklemek ve DLL 'deki işlevlere çağrıları uygulamak için kod içerir. İçeri aktarma kitaplığındaki bir dış işlevin bulunması, bağlayıcının bu işlev için kodun bir DLL içinde olduğunu bildirir. Dll 'Lerin dış başvurularını çözümlemek için bağlayıcı, sisteme, işlem başladığında DLL kodunu nerede bulacağını belirten yürütülebilir dosyaya bilgi ekler.

Sistem dinamik bağlantılı başvurular içeren bir programı başlattığında, gerekli dll 'Leri bulmak için programın yürütülebilir dosyasındaki bilgileri kullanır. DLL 'yi bulamazsa, sistem işlemi sonlandırır ve hatayı raporlayan bir iletişim kutusu görüntüler. Aksi takdirde, sistem DLL modüllerini işlemin adres alanına eşler.

Dll 'lerden herhangi biri gibi başlatma ve sonlandırma kodu `DllMain`için bir giriş noktası işlevi varsa, işletim sistemi işlevini çağırır. Giriş noktası işlevine geçirilen parametrelerden biri, DLL 'nin işleme ilişdiğini belirten bir kodu belirtir. Giriş noktası işlevi TRUE döndürmezse, sistem işlemi sonlandırır ve hatayı raporlar.

Son olarak, sistem, DLL işlevleri için başlangıç adreslerini sağlamak üzere işlemin yürütülebilir kodunu değiştirir.

Programın kodunun geri kalanı gibi, DLL kodu, işlem başladığında işlemin adres alanına eşlenir ve yalnızca gerektiğinde belleğe yüklenir. Sonuç olarak, `PRELOAD` Windows 'un önceki `LOADONCALL` sürümlerinde yüklemeyi denetlemek için. def dosyaları tarafından kullanılan ve kod özniteliklerinin artık anlamı yoktur.

### <a name="explicit-linking"></a>Açık bağlama

Çoğu uygulama, kullanılacak en kolay bağlama yöntemi olduğundan örtük bağlama kullanır. Ancak, Açık bağlama gereken durumlar da vardır. Açık bağlama kullanmanın bazı yaygın nedenleri aşağıda verilmiştir:

- Uygulama, çalışma zamanına kadar yüklediği DLL 'nin adını bilmez. Örneğin, uygulama DLL adını ve başlangıç olarak bir yapılandırma dosyasından aktarılmış işlevleri alabilir.

- İşlem başlangıcında DLL bulunamazsa, örtük bağlama kullanan bir işlem işletim sistemi tarafından sonlandırılır. Açık bağlama kullanan bir işlem bu durumda sonlandırılmaz ve hatadan kurtarmayı deneyebilir. Örneğin, işlem hatayı kullanıcıya bildirebilir ve kullanıcının DLL 'ye başka bir yol belirtmesini sağlayabilir.

- Dolaylı bağlama kullanan bir işlem, bağlı olduğu dll 'lerden herhangi biri başarısız olan bir `DllMain` işleve sahip olursa da sonlandırılır. Açık bağlama kullanan bir işlem bu durumda sonlandırmaz.

- Windows, uygulama yüklendiğinde tüm dll 'Leri yüklediği için, birden çok dll 'ye örtülü olarak bağlanan bir uygulama başlatılabilir. Başlangıç performansını geliştirmek için, bir uygulama yalnızca yüklemeden hemen sonra gerekli olan DLL 'lere bağlanabilir ve bunlara açıkça bağlantı için diğer dll 'Lerin gerekli olana kadar bekler.

- Açık bağlama, bir içeri aktarma kitaplığı kullanarak uygulamayı bağlama gereksinimini ortadan kaldırır. DLL 'deki değişiklikler dışa aktarma sıra sayımlarından oluşmasına neden olursa, Açık bağlama kullanan uygulamaların bir sıra değeri değil bir işlevin adını kullanarak `GetProcAddress` çağrı yaptığı durumlarda yeniden bağlanması gerekmez, ancak örtük bağlama kullanan uygulamalar, yeni içeri aktarma kitaplığı.

Aşağıda, Açık bağlama konusunda bilinmesi için iki tehlikeli yer verilmiştir:

- DLL 'de bir `DllMain` giriş noktası işlevi varsa, işletim sistemi işlevini çağıran iş parçacığı `LoadLibrary`bağlamında çağırır. Önceki bir çağrı, `LoadLibrary` `FreeLibrary` işleve karşılık gelen hiçbir çağrısı olmadığı için, dll zaten işleme eklenmişse, giriş noktası işlevi çağrılmaz. DLL bir işlemin her iş parçacığı için başlatma gerçekleştirmek üzere `DllMain` bir işlev kullanıyorsa açık bağlama soruna neden olabilir çünkü `LoadLibrary` (veya `AfxLoadLibrary`) çağrıldığında zaten var olan iş parçacıkları başlatılmaz.

- Bir dll, olarak `__declspec(thread)`statik uzantı verileri bildiriyorsa, açıkça bağlanmışsa koruma hatasına neden olabilir. DLL bir çağrısı `LoadLibrary`tarafından yüklendikten sonra, kod bu verilere başvurduğunda bir koruma hatasına neden olur. (Statik kapsam verileri hem genel hem de yerel statik öğeleri içerir.) Bu nedenle, bir DLL oluşturduğunuzda, iş parçacığı yerel depolama kullanmaktan kaçının veya dll kullanıcılarını dinamik olarak DLL 'niz yükleme olasılığı hakkında bilgilendirmelisiniz. Daha fazla bilgi için bkz. [dinamik bağlantı kitaplığında iş parçacığı yerel depolama alanı kullanma (Windows SDK)](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library).

<a name="linking-implicitly"></a>

## <a name="link-an-executable-to-a-dll"></a>Bir yürütülebilir dosyayı DLL’ye bağlama

Bir DLL 'yi örtük bağlama ile kullanmak için, istemci yürütülebilir dosyalarının bu dosyaları DLL sağlayıcısından alması gerekir:

- DLL 'de, yayımlanan verilerin, işlevlerin ve/veya C++ sınıfların bildirimlerini içeren bir veya daha fazla üst bilgi dosyası (. h dosyası). DLL tarafından dışarıya alınan sınıfların, işlevlerin ve verilerin tümü üst bilgi dosyasında işaretlenmelidir `__declspec(dllimport)` . Daha fazla bilgi için bkz. [dllexport, dllimport](../cpp/dllexport-dllimport.md).

- Yürütülebilire bağlanacak bir içeri aktarma kitaplığı. Bağlayıcı, DLL yapılandırıldığında içeri aktarma kitaplığını oluşturur. Daha fazla bilgi için bkz [. LIB dosyaları](reference/dot-lib-files-as-linker-input.md).

- Gerçek DLL dosyası.

Bir DLL 'yi örtük bağlama ile kullanmak için, yürütülebilir dosya, işlevler ve sınıflar için çağrılar içeren her bir kaynak dosyasında C++ dll tarafından içe aktarılmış verileri, işlevleri veya sınıfları bildiren üst bilgi dosyalarını içermelidir. Kodlama perspektifinden, dışarıya aktarılmış işlevlere yapılan çağrılar tıpkı diğer işlev çağrıları gibi.

Çağıran yürütülebilir dosyayı oluşturmak için içeri aktarma kitaplığıyla bağlamanız gerekir. Dış makefile veya derleme sistemi kullanıyorsanız, diğer nesne (. obj) dosyalarını veya bağlantı oluşturduğunuz kitaplıkları listeettiğiniz içeri aktarma kitaplığının dosya adını belirtin.

İşletim sisteminin, çağıran yürütülebilir dosyayı yüklediğinde DLL dosyasını bulabilmeleri gerekir. Bu, uygulamanız yüklendiğinde uygulamanızın DLL varlığını dağıtması veya doğrulaması gerektiği anlamına gelir.

<a name="linking-explicitly"></a>

## <a name="how-to-link-explicitly-to-a-dll"></a>Bir DLL 'ye açıkça bağlantı oluşturma

Bir DLL 'yi açık bağlama ile kullanmak için, uygulamaların çalışma zamanında DLL 'yi açıkça yüklemesi için bir işlev çağrısı yapması gerekir. Bir DLL 'ye açıkça bağlantı sağlamak için bir uygulamanın şunları yapmanız gerekir:

- DLL [](loadlibrary-and-afxloadlibrary.md)'yi yüklemek `LoadLibraryEx`ve bir modül tanıtıcısı almak için LoadLibrary, veya benzer bir işlev çağırın.

- Uygulamanın çağırdığı her bir içe aktarılmış işleve bir işlev işaretçisi almak için [GetProcAddress](getprocaddress.md) çağrısı yapın. Uygulamalar, DLL işlevlerini bir işaretçi aracılığıyla çağırdığından, derleyici dış başvuru oluşturmaz, bu nedenle içeri aktarma kitaplığıyla bağlantı oluşturmanız gerekmez. Ancak, çağrısı yaptığınız aktarılmış işlevlerin `typedef` çağrı `using` imzasını tanımlayan bir veya deyiminiz olmalıdır.

- DLL ile işiniz bittiğinde [FreeLibrary](freelibrary-and-afxfreelibrary.md) ' i çağırın.

Örneğin, bu örnek işlev "myDll" adlı bir DLL yüklemek için çağırır `LoadLibrary` , "DLLFunc1" adlı bir işleve işaretçi almak için çağırır `GetProcAddress` , işlevi çağırır ve sonucu kaydeder ve sonra dll 'yi kaldırmak için çağırır `FreeLibrary` .

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

Bu örnekte aksine, çoğu durumda belirli bir dll için uygulamanızda `LoadLibrary` `FreeLibrary` yalnızca bir kez çağrı yapmanız gerekir, özellikle de dll 'de birden çok işlev çağıracaksanız veya DLL işlevlerini sürekli olarak çağırabilirsiniz.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [İçeri Aktarma Kitaplıkları ve Dışarı Aktarma Dosyalarıyla Çalışma](reference/working-with-import-libraries-and-export-files.md)

- [Dinamik bağlantı kitaplığı arama sırası](/windows/win32/Dlls/dynamic-link-library-search-order)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'daC++ C/dll oluşturma](dlls-in-visual-cpp.md)
