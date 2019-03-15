---
title: Bir DLL'ye bağlandığı bir yürütülebilir dosya
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
ms.openlocfilehash: fc7a676059af17e7a42189c7c15ca157a081e08a
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2019
ms.locfileid: "57818368"
---
# <a name="link-an-executable-to-a-dll"></a>Bir DLL'ye bağlandığı bir yürütülebilir dosya

Bir yürütülebilir dosya bağlar (veya yükler) bir DLL iki yoldan biriyle:

- *Örtük bağlama*, burada yürütülebilir onu kullanarak yüklendiğinde işletim sistemi DLL'yi yükler. İstemci yürütülebilir dosyanın yalnızca işlevleri statik olarak bağlı ve yürütülebilirin gibi DLL'nin dışarı aktarılan işlevleri çağırır. Örtük bağlama bazen olarak adlandırılır *statik yük* veya *yükleme zamanı dinamik bağlama*.

- *Açık bağlama*, burada DLL çalışma zamanında isteğe bağlı işletim sistemi yükler. Açık bağlama tarafından DLL kullanan yürütülebilir bir dosya, işlev çağrıları açıkça yüklemek ve DLL'yi ve DLL tarafından dışarı aktarılan işlevlerine erişmek için yapmanız gerekir. Statik olarak bağlı bir kitaplığı işlevleri çağrısına farklı olarak, istemci yürütülebilir bir işlev işaretçisi aracılığıyla DLL'de dışa aktarılan işlevleri çağırmalıdır. Açık bağlama bazen olarak adlandırılır *dinamik yük* veya *çalışma zamanı dinamik bağlama*.

Bir yürütülebilir dosya için aynı DLL'yi bağlamak için ya da bağlama yöntemini kullanabilirsiniz. Ayrıca, bu yöntemleri birbirini dışlamaz; bir yürütülebilir dosyayı DLL'ye örtük olarak bağlayabilirsiniz ve başka açıkça iliştirebilirsiniz.

<a name="determining-which-linking-method-to-use"></a>

## <a name="link-an-executable-to-a-dll"></a>Bir DLL'ye bağlandığı bir yürütülebilir dosya

Örtük bağlama veya açık bağlama kullanmak için uygulamanız için yapmanız gereken, mimari bir karardır. Avantajlar ve dezavantajlar her yöntem için vardır.

### <a name="implicit-linking"></a>Örtük bağlama

Bir uygulamanın kodu dışarı aktarılan bir DLL işlevini çağırdığında örtük bağlama gerçekleşir. Çağrıyı yapan yürütülebilir dosya için kaynak kodu derlendiğinde veya DLL işlev çağrısı bir dış işlev başvurusu nesne kodu oluşturur. Bu dış başvurunun gidermek için uygulamaya DLL yapıcı tarafından sağlanan içeri aktarma kitaplığına (.lib dosyası) bağlamanız gerekir.

İçeri aktarma kitaplığı yalnızca DLL'yi yüklemeye ve DLL'deki işlevleri çağrıları uygulamak için kodu içerir. Bir dış işlevi, bir içeri aktarma kitaplığına bulma, bağlayıcı söz konusu işlevin kodu bir DLL içinde olduğunu bildirir. DLL'leri dış başvuruları çözümlemek için bağlayıcı yalnızca bilgi işlem başlatıldığında DLL kodun bulunacağı yeri sisteme söyler yürütülebilir dosyaya ekler.

Dinamik olarak bağlı başvurular içeren bir program sistem başlatıldığında, gerekli DLL'lerin yerini belirlemek için programın yürütülebilir dosyada bilgileri kullanır. DLL bulamazsanız, sistem işlemi sonlandırır ve hata raporlarını bir iletişim kutusu görüntüler. Aksi takdirde, sistem DLL modülleri işlemin adres alanına eşler.

DLL varsa başlatma ve sonlandırma kodu için bir giriş noktası işlevi gibi `DllMain`, işletim sistemi işlevi çağırır. Giriş noktası işleve geçirilen parametrelerden biri, DLL gösteren bir kod işleme iliştiriyor belirtir. Giriş noktası işlevi TRUE döndürmezse, sistem işlemi sonlandırır ve hata bildirir.

Son olarak, sistem DLL işlevleri için başlangıç adresi sağlamak için işlemin yürütülebilir kodu değiştirir.

Bir program kodunuza gibi geri kalan, işlemi başlatılır ve yalnızca gerektiğinde belleğe yüklenen DLL kodu işlemin adres alanına eşlenir. Sonuç olarak, `PRELOAD` ve `LOADONCALL` önceki Windows sürümlerinde artık yükleme için .def dosyaları tarafından kullanılan kod özniteliklerinin anlamı yoktur.

### <a name="explicit-linking"></a>Açık bağlama

Çoğu uygulama, çünkü bu kolay bağlama yönteminin kullanılacağını örtük bağlama kullanın. Ancak, açıkça bağlama ne zaman gerekli olduğu durumlar da vardır. Açık bağlama kullanmak için bazı yaygın nedenler şunlardır:

- Uygulama çalışma zamanına kadar yükleyen bir DLL adı bilmez. Örneğin, uygulama başlatma sırasında bir yapılandırma dosyasından adını DLL ve dışarı aktarılan işlevleri elde edebilirsiniz.

- Örtük bağlama kullanan bir işleme DLL işlem başlangıçta bulunmazsa işletim sistemi tarafından sonlandırıldı. Açık bağlama kullanan bir işlem, bu durumda sonlandırılmadı ve hatadan kurtarmayı deneyebilir. Örneğin, işlem hatayla ilgili kullanıcıyı bilgilendir ve kullanıcının başka bir DLL yolu belirtin.

- Örtük bağlama kullanan bir işlem için bağlı olduğu DLL'lerin varsa da sonlandırılır bir `DllMain` başarısız işlev. Açık bağlama kullanan bir işlem, bu durumda sonlandırılmadı.

- Çok fazla örtük olarak bağlanan bir uygulama uygulama yüklenirken Windows DLL'leri yüklediğinden başlatmak yavaş olabilir. Başlangıç performansı artırmak için uygulamanın yalnızca onlara açıkça bağlanmak için gereken diğer DLL'leri kadar hemen yüklenirken bekleyin sonra gereken, bu DLL'leri örtük olarak bağlayabilirsiniz.

- Açık bağlama, bir içeri aktarma kitaplığını kullanarak bağlantı gereksinimini ortadan kaldırır. Değiştirmek dışa aktarma sıra sayıları DLL değişiklikleri neden oluyorsa, açık bağlama kullanan uygulamaları bunlar çağırırsanız yeniden bağlamak zorunda değilsiniz `GetProcAddress` örtük bağlama kullanan uygulamalar için yeniden bağlamak gerekir ancak bir işlev ve sıralı bir değer değil, adını kullanarak yeni içeri aktarma kitaplığı.

Dikkat edilmesi gereken açık bağlama iki riskleri şunlardır:

- DLL varsa bir `DllMain` giriş noktası işlevini, işletim sistemini çağıran işlevi çağıran iş parçacığının bağlamında `LoadLibrary`. DLL, önceki arama nedeniyle işleme zaten bağlıysa, giriş noktası işlevi çağrılmaz `LoadLibrary` karşılık gelen hiçbir çağrı vardı, `FreeLibrary` işlevi. Açık bağlama sorunlara DLL kullanıyorsa bir `DllMain` iş parçacığı zaten mevcut olduğundan bir işlem için her iş parçacığı başlatma gerçekleştirmek için işlevi zaman `LoadLibrary` (veya `AfxLoadLibrary`) olarak adlandırılır başlatılmaz.

- Bir DLL olarak statik kapsam verileri bildirirse `__declspec(thread)`, onu açıkça bağlı koruma hatasına neden olabilir. DLL için bir çağrı tarafından yüklendikten sonra `LoadLibrary`, her kod başvurduğunda bu veri koruma hatasına neden olur. (Statik kapsam verileri hem genel hem de yerel statik öğeler içerir.) Bu nedenle, bir DLL oluşturduğunuzda, iş parçacığı-yerel depolamayı kullanmaktan kaçının veya dinamik olarak, DLL yükleme olası Tuzaklar hakkında DLL varsayılandır. Daha fazla bilgi için [iş parçacığında yerel depolama dinamik bağlantı kitaplığı (Windows SDK) kullanarak](/windows/desktop/Dlls/using-thread-local-storage-in-a-dynamic-link-library).

<a name="linking-implicitly"></a>

## <a name="link-an-executable-to-a-dll"></a>Bir DLL'ye bağlandığı bir yürütülebilir dosya

Örtük bağlama bir DLL kullanmak için İstemci yürütülebilir dosyaları, DLL sağlayıcısından bu dosyaları edinmeniz gerekir:

- Dışarı aktarılan verileri, işlevleri ve/veya C++ sınıfları dll bildirimlerini içeren bir veya daha fazla üst bilgi dosyaları (.h). Sınıflar, İşlevler ve DLL tarafından dışarı aktarılan verileri tüm işaretlenmelidir `__declspec(dllimport)` üstbilgi dosyasında. Daha fazla bilgi için [dllexport, dllimport](../cpp/dllexport-dllimport.md).

- Yürütülebilir dosyanın içine bağlamak için içeri aktarma kitaplığı. Bağlayıcı, DLL derlenirken içeri aktarma kitaplığı oluşturur. Daha fazla bilgi için [. LIB dosyaları](reference/dot-lib-files-as-linker-input.md).

- Gerçek DLL dosyası.

Örtük bağlama bir DLL kullanmak için veri, İşlevler veya dışarı aktarılan verileri, işlevleri ve sınıfları için çağrılar içerdiğini her kaynak dosyasındaki DLL tarafından dışarı aktarılan C++ sınıfları bildirme üst bilgi dosyaları yürütülebilir bir dosya içermelidir. Kodlama açısından bakıldığında, dışa aktarılan işlevlere herhangi bir diğer işlev çağrısıyla çağrılarıdır.

Çağıran yürütülebilir dosyanın derleme içeri aktarma kitaplığı ile bağlanmanız gerekir. Harici bir derleme görevleri dosyası veya yapı sistemi kullanıyorsanız, bağlantı kitaplıkları veya diğer nesne (.obj) dosyaları listesinde nerede içeri aktarma kitaplığı dosya adı belirtin.

İşletim sistemini çağıran yürütülebilir dosya yüklediğinde, DLL dosyasını bulabilir olması gerekir. Bu, uygulamanızı dağıtmak gerekir veya uygulama yüklendiğinde DLL varlığını doğrulamak anlamına gelir.

<a name="linking-explicitly"></a>

## <a name="how-to-link-explicitly-to-a-dll"></a>Açıkça bir DLL'ye bağlama

Açık bağlama bir DLL kullanmak için uygulamaları DLL çalışma zamanında açıkça yüklemek için işlev çağrısı yapmalısınız. Bir DLL'ye açıkça bağlanmak için bir uygulama gerekir:

- Çağrı [LoadLibrary](loadlibrary-and-afxloadlibrary.md), `LoadLibraryEx`, veya DLL'yi yüklemeye ve modül tanıtıcısı almak için benzer bir işlev.

- Çağrı [GetProcAddress](getprocaddress.md) her bir işlev işaretçisi elde etmek için uygulamayı çağıran işlev dışarı. İşaretçi üzerinden DLL işlevleri çağırmak için derleyici bir içeri aktarma kitaplığı ile bağlantı gerekmez. Bu nedenle dış başvuruları oluşturmaz. Ancak, olmalıdır bir `typedef` veya `using` çağrı imzası, arama dışarı aktarılan işlevlerin tanımlayan ifade.

- Çağrı [FreeLibrary](freelibrary-and-afxfreelibrary.md) DLL ile işiniz bittiğinde.

Örneğin, bu örnek işlev çağrıları `LoadLibrary` "MyDLL" adlı bir dll'yi çağıran `GetProcAddress` "DLLFunc1" adlı bir işlev işaretçisi elde etmek için işlevini çağırır ve sonucu kaydeder ve sonra çağıran `FreeLibrary` DLL'yi.

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

Farklı olarak bu örnekte, çoğu durumda çağırmalısınız `LoadLibrary` ve `FreeLibrary` uygulamanızda özellikle birden fazla DLL işlevlerini veya DLL arama için kullanacaksanız belirli bir DLL için yalnızca bir kez art arda işlevleri.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [İçeri Aktarma Kitaplıkları ve Dışarı Aktarma Dosyalarıyla Çalışma](reference/working-with-import-libraries-and-export-files.md)

- [Dinamik bağlantı kitaplığı arama sırası](/windows/desktop/Dlls/dynamic-link-library-search-order)

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++'ta DLL'ler](dlls-in-visual-cpp.md)
