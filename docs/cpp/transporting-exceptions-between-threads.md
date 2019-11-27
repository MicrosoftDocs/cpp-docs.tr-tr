---
title: Özel durumları iş parçacıkları arasında taşıma
ms.date: 05/07/2019
helpviewer_keywords:
- std::current_exception
- transporting exceptions between threads
- std::copy_exception
- exception_ptr
- std::exception_ptr
- std::rethrow_exception
- current_exception
- transport exceptions between threads
- copy_exception
- rethrow_exception
- move exceptions between threads
ms.assetid: 5c95d57b-acf5-491f-8122-57c5df0edd98
ms.openlocfilehash: 25b09c508b932a4d1470f6b23f03aa52e62c68cc
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246307"
---
# <a name="transporting-exceptions-between-threads"></a>Özel durumları iş parçacıkları arasında taşıma

Microsoft C++ DERLEYICISI (MSVC) bir *özel durumun* bir iş parçacığından diğerine taşınmasını destekler. Taşınan özel durumlar bir iş parçacığındaki özel durumu yakalamanızı sağlar ve sonra özel durumun farklı bir iş parçacığında oluşmuş gibi görünmesini sağlar. Örneğin, bu özelliği birincil iş parçacığının ikincil iş parçacıkları tarafından oluşturulan tüm özel durumları işlediği çok iş parçacıklı bir uygulamayı yazmak için kullanabilirsiniz. Özel durum taşımaları, çoğunlukla paralel programlama kitaplıkları veya sistemleri oluşturan geliştiriciler için yararlıdır. MSVC, taşıma özel durumlarını uygulamak için [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) türünü ve [current_exception](../standard-library/exception-functions.md#current_exception), [rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)ve [make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr) işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace std
{
   typedef unspecified exception_ptr;
   exception_ptr current_exception();
   void rethrow_exception(exception_ptr p);
   template<class E>
       exception_ptr make_exception_ptr(E e) noexcept;
}
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Memesi*|`exception_ptr` türünü uygulamak için kullanılan belirtilmemiş bir iç sınıf.|
|*Lama*|Bir özel duruma başvuran `exception_ptr` nesnesi.|
|*A*|Bir özel durumu temsil eden sınıf.|
|*a*|Parametre `E` sınıfı örneği.|

## <a name="return-value"></a>Dönüş değeri

`current_exception` işlevi, şu anda sürmekte olan özel duruma başvuran bir `exception_ptr` nesnesi döndürür. Eğer devam eden bir özel durum yoksa, işlev herhangi bir özel durumla ilişkilendirilmemiş bir `exception_ptr` nesnesi döndürür.

`make_exception_ptr` işlevi, *e* parametresi tarafından belirtilen özel duruma başvuran bir `exception_ptr` nesnesi döndürür.

## <a name="remarks"></a>Açıklamalar

### <a name="scenario"></a>Senaryo

Bir değişkenin çalışma miktarını işleyebilmek için ölçeklenebilen bir uygulama oluşturmak istediğinizi düşünün. Bunu gerçekleştirmek için çok iş parçacıklı bir uygulama tasarlayın; bu uygulamada ilk, birincil iş parçacığı işi yapmak için gereken sayıda ikincil iş parçacığını oluşturur. İkincil iş parçacıkları yükleri dengelemek, verimi artırmak ve kaynakları yönetmek için birincil iş parçacıklarına yardımcı olur. İşi dağıtarak, çok iş parçacıklı uygulamalar tek iş parçacıklı uygulamalardan daha iyi performans gösterir.

Ancak, ikincil bir iş parçacığı bir özel durum oluşturursa, birincil iş parçacığının bu durumu işlemesini istersiniz. Bunun nedeni, ikincil iş parçacığı sayısı ne olursa olsun uygulamanızın tutarlı ve birleştirilmiş bir şekilde özel durumları işlemesini istemenizdir.

### <a name="solution"></a>Çözüm

C++ Standard, önceki senaryonun işlenmesi için, bir özel durumun iş parçacıkları arasında taşınmasını destekler. İkincil bir iş parçacığı bir özel durum oluşturursa, bu özel durum *geçerli özel durum*olur. Benzerleme vurguladı ile gerçek dünyaya, geçerli özel durumun *uçuş*aşamasında olduğu söylenir. Geçerli özel durum, özel durum işleyicisi tarafından dönüşü yakalanana kadar uçuştadır.

İkincil iş parçacığı, bir **catch** bloğunda geçerli özel durumu yakalayabilir ve sonra özel durumu bir `exception_ptr` nesnesine depolamak için `current_exception` işlevini çağırabilir. `exception_ptr` nesnesi ikincil iş parçacığı ve birincil iş parçacığı için kullanılabilir olmalıdır. Örneğin, `exception_ptr` nesnesi, erişimi bir mutex tarafından denetlenen genel bir değişken olabilir. *Özel durum taşıma* terimi, bir iş parçacığında bir özel durumun başka bir iş parçacığı tarafından erişilebilen bir biçime dönüştürülebileceği anlamına gelir.

Ardından, birincil iş parçacığı, `exception_ptr` nesnesinden özel durumu çıkaran ve sonra oluşturan `rethrow_exception` işlevini çağırır. Özel durum oluştuğunda, birincil iş parçacığındaki geçerli özel durum haline gelir. Diğer bir deyişle, özel durum birincil iş parçacığında oluşmuş görünür.

Son olarak, birincil iş parçacığı geçerli özel durumu bir **catch** bloğunda yakalayabilir ve sonra işleyebilir veya daha yüksek düzeydeki bir özel durum işleyicisine atar. Ya da birincil iş parçacığı özel durumu yoksayar ve işlemi sonlandırmaya izin verir.

Çoğu uygulamada özel durumların iş parçacıkları arasında taşınması gerekmez. Ancak, sistem işi ikincil iş parçacıkları, işlemci veya çekirdek arasında bölebildiğinden, bu özellik paralel bir bilgi işlem sisteminde yararlıdır. Paralel bir bilgi işlem ortamında, tek ve özel bir iş parçacığı ikincil iş parçacıklarından gelen tüm özel durumları işleyebilir ve herhangi bir uygulama için tutarlı bir özel durum işleme modeli sunabilir.

C++ Standartları komitesi teklifi hakkında daha fazla bilgi için, internette "Özel Durumları İş Parçacıkları Arasında Taşıma için Dil Desteği" başlıklı N2179 belge numarasını arayın.

### <a name="exception-handling-models-and-compiler-options"></a>Özel durum işleme modelleri ve derleyici seçenekleri

Uygulamanızın özel durum işleme modeli, bir özel durumu yakalayıp taşıyabileceğini ya da bunu yapamayacağınızı belirler. Visual C+; C++ özel durumlarını, yapılandırılmış özel durum işleme (SEH) özel durumlarını ve ortak dil çalışma zamanı (CLR) özel durumlarını işleyebilen üç modeli destekler. Uygulamanızın özel durum işleme modelini belirtmek için [/Eh](../build/reference/eh-exception-handling-model.md) ve [/clr](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneklerini kullanın.

Yalnızca aşağıdaki derleyici seçeneklerinin ve programlama deyimlerinin birleşimi bir özel durumu taşıyabilir. Diğer birleşimler özel durumları yakalayamaz ya da özel durumları yakalasa da taşıyamaz.

- **/EHa** derleyici seçeneği ve **catch** deyimleri, SEH ve C++ özel durumları taşıyabilir.

- **/EHa**, **/EHS**ve **/EHsc** derleyici seçenekleri ve **catch** deyimleri C++ özel durumları taşıyabilir.

- **/Clr** derleyici seçeneği ve **catch** deyimleri C++ özel durumları taşıyabilir. **/Clr** derleyici seçeneği, **/EHa** seçeneğinin belirtimini gerektirir. Derleyicinin yönetilen özel durumların taşınmasını desteklemediğini unutmayın. Bunun nedeni, [System. Exception sınıfından](../standard-library/exception-class.md)türetilen yönetilen özel durumların, ortak dil çalışma zamanının tesislerini kullanarak iş parçacıkları arasında taşıyabildiğiniz bir nesnelerdir.

   > [!IMPORTANT]
   > **/EHsc** derleyici seçeneğini belirtmenizi ve yalnızca C++ özel durumları yakalanmasını öneririz. **/EHa** veya **/clr** derleyici seçeneğini ve üç nokta *özel durum bildirimi* (`catch(...)`) ile bir **catch** bildirimini kullanırsanız, kendinizi bir güvenlik tehditlerine maruz olursunuz. Büyük olasılıkla bazı özel durumları yakalamak için **catch** ifadesini kullanmayı amaçlarsınız. Ancak, `catch(...)` ifade, önemli olması C++ gereken beklenmeyen olanlar da dahil olmak üzere All ve SEH özel durumlarını yakalar. Beklenmeyen bir özel durumu yoksayarsanız ya da düzgün işleyemezseniz, kötü amaçlı yazılımlar programınızın güvenliğine zarar vermek için bu fırsatı kullanabilir.

## <a name="usage"></a>Kullanım

Aşağıdaki bölümlerde, `exception_ptr` türü ve `current_exception`, `rethrow_exception`ve `make_exception_ptr` işlevleri kullanılarak özel durumların nasıl taşınması anlatılmaktadır.

## <a name="exception_ptr-type"></a>exception_ptr türü

Geçerli özel duruma veya Kullanıcı tarafından belirtilen özel durum örneğine başvurmak için bir `exception_ptr` nesnesi kullanın. Microsoft uygulamasında bir özel durum [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) yapısıyla temsil edilir. Her `exception_ptr` nesnesi, özel durumu temsil eden `EXCEPTION_RECORD` yapısının bir kopyasına işaret eden bir özel durum başvurusu alanı içerir.

Bir `exception_ptr` değişkeni bildirdiğinizde, değişken herhangi bir özel durumla ilişkili değildir. Diğer bir deyişle, özel durum başvuru alanı NULL olur. Böyle bir `exception_ptr` nesnesine *null exception_ptr*denir.

Bir `exception_ptr` nesnesine özel durum atamak için `current_exception` veya `make_exception_ptr` işlevini kullanın. Bir `exception_ptr` değişkenine bir özel durum atadığınızda, değişkenin özel durum başvuru alanı özel durumun bir kopyasına işaret eder. Özel durumu kopyalamak için yeterli bellek yoksa, özel durum başvuru alanı bir [std:: bad_alloc](../standard-library/bad-alloc-class.md) özel durumunun kopyasına işaret eder. `current_exception` veya `make_exception_ptr` işlevi başka bir nedenle özel durumu kopyalayamayabilir, işlev geçerli işlemden çıkmak için [Terminate](../c-runtime-library/reference/terminate-crt.md) işlevini çağırır.

Adına rağmen, bir `exception_ptr` nesnesi kendisi bir işaretçi değildir. İşaretçi semantiğini etkilemez ve işaretçi üye erişimi (`->`) veya yöneltme (`*`) işleçleriyle kullanılamaz. `exception_ptr` nesnenin ortak veri üyeleri veya üye işlevleri yok.

### <a name="comparisons"></a>Karşılaştırma

İki `exception_ptr` nesnesini karşılaştırmak için eşittir (`==`) ve Not-eşit (`!=`) işleçlerini kullanabilirsiniz. İşleçler, özel durumları temsil eden `EXCEPTION_RECORD` yapılarının ikili değerini (bit düzeniyle) karşılaştırmaz. Bunun yerine, işleçler `exception_ptr` nesnelerinin özel durum başvurusu alanındaki adresleri karşılaştırır. Sonuç olarak, null `exception_ptr` ve NULL değeri eşit olarak karşılaştırılmaktadır.

## <a name="current_exception-function"></a>current_exception işlevi

Bir **catch** bloğunda `current_exception` işlevini çağırın. Bir özel durum uçuş durumunda ve **catch** bloğu özel durumu yakalayabiliyorsanız, `current_exception` işlevi özel duruma başvuran bir `exception_ptr` nesnesi döndürür. Aksi takdirde, işlev null `exception_ptr` bir nesne döndürür.

### <a name="details"></a>Ayrıntılar

`current_exception` işlevi, **catch** ifadesinin bir [özel durum bildirimi](../cpp/try-throw-and-catch-statements-cpp.md) bildirimi belirttiğinden bağımsız olarak uçuş durumunda olan özel durumu yakalar.

Özel durumu yeniden oluşturmazsınız, geçerli özel durum için yok edici **catch** bloğunun sonunda çağırılır. Ancak, yıkıcı içinde `current_exception` işlevini çağırsanız bile, işlev geçerli özel duruma başvuran bir `exception_ptr` nesnesi döndürür.

`current_exception` işleve art arda yapılan çağrılar, geçerli özel durumun farklı kopyalarına başvuran `exception_ptr` nesneleri döndürür. Sonuç olarak, kopyalar aynı ikili değerde olsalar da farklı kopyalara başvurduklarından, nesneler eşit olmayarak karşılaştırılır.

### <a name="seh-exceptions"></a>SEH özel durumları

**/EHa** derleyici seçeneğini kullanırsanız, bir C++ SEH özel durumunu **catch** bloğunda yakalayabilirsiniz. `current_exception` işlevi, SEH özel durumuna başvuran bir `exception_ptr` nesnesi döndürür. `rethrow_exception` işlevi, bağımsız değişkeni olarak thetranted `exception_ptr` nesnesi ile çağırırsanız SEH özel durumunu oluşturur.

`current_exception` işlevi bir SEH **__finally** sonlandırma işleyicisine, **__except** özel durum işleyicisine veya **__except** filtre ifadesine çağırırsanız null `exception_ptr` döndürür.

Taşınan özel durumlar iç içe geçmiş özel durumları desteklemez. Bir iç içe geçmiş özel durum, bir özel durum işlenirken başka bir özel durumun oluşturulmasıyla ortaya çıkar. İç içe geçmiş bir özel durumu yakalarsanız, `EXCEPTION_RECORD.ExceptionRecord` veri üyesi ilişkili özel durumları tanımlayan bir `EXCEPTION_RECORD` yapıları zincirine işaret eder. `current_exception` işlevi, `ExceptionRecord` veri üyesi sıfırlandı `exception_ptr` bir nesne döndürdüğünden iç içe özel durumları desteklemez.

Bir SEH özel durumu yakalarsanız, `EXCEPTION_RECORD.ExceptionInformation` veri üyesi dizisindeki herhangi bir işaretçi tarafından başvurulan belleği yönetmeniz gerekir. Belleğin, karşılık gelen `exception_ptr` nesnesinin kullanım ömrü boyunca geçerli olduğunu ve `exception_ptr` nesnesi silindiğinde belleğin serbest olduğunu garanti etmeniz gerekir.

Yapılandırılmış özel durum (SE) çevirici işlevlerini özel durumları taşıma özelliğiyle birlikte kullanabilirsiniz. Bir SEH özel durumu bir C++ özel duruma çevrilmişse, `current_exception` IşLEVI özgün SEH özel durumu yerine çevrilmiş özel duruma başvuran bir `exception_ptr` döndürür. `rethrow_exception` işlevi, özgün özel durumu değil, daha sonra çevrilmiş özel durumu oluşturur. İ çevirici işlevleri hakkında daha fazla bilgi için bkz. [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).

## <a name="rethrow_exception-function"></a>rethrow_exception işlevi

Yakalanan bir özel durumu bir `exception_ptr` nesnesinde depoladıktan sonra, birincil iş parçacığı nesneyi işleyebilir. Birincil iş parçacığındaki bağımsız değişkeni olarak `exception_ptr` nesnesiyle birlikte `rethrow_exception` işlevini çağırın. `rethrow_exception` işlevi, özel durumu `exception_ptr` nesnesinden ayıklar ve ardından birincil iş parçacığı bağlamında özel durumu oluşturur. `rethrow_exception` işlevinin *p* parametresi null `exception_ptr`ise, işlev [std:: bad_exception](../standard-library/bad-exception-class.md)atar.

Ayıklanan özel durum artık birincil iş parçacığında geçerli özel durumdur ve diğer özel durumlar gibi onu işleyebilirsiniz. Özel durumu yakalarsanız, hemen işleyebilir veya bir **throw** ifadesini kullanarak daha yüksek düzey özel durum işleyicisine gönderebilirsiniz. Aksi halde, hiçbir şey yapmayın ve varsayılan sistem özel durum işleyicisinin işlemi sonlandırmasına izin verin.

## <a name="make_exception_ptr-function"></a>make_exception_ptr işlevi

`make_exception_ptr` işlevi, bağımsız değişkeni olarak bir sınıfın örneğini alır ve sonra örneğe başvuran bir `exception_ptr` döndürür. Genellikle, bir [özel durum sınıfı](../standard-library/exception-class.md) nesnesini `make_exception_ptr` işlevine bağımsız değişken olarak belirtirsiniz, ancak herhangi bir sınıf nesnesi bağımsız değişken olabilir.

`make_exception_ptr` işlevini çağırmak, C++ özel durum atma, bir **catch** bloğunda yakalama ve sonra özel duruma başvuran bir `exception_ptr` nesnesi döndürmek için `current_exception` işlevini çağırma ile eşdeğerdir. `make_exception_ptr` işlevin Microsoft uygulamasında uygulanması daha etkilidir ve bir özel durum yakalanmasıdır.

Uygulama genellikle `make_exception_ptr` işlevi gerektirmez ve kullanımını önermiyoruz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, standart C++ özel durumunu ve özel bir C++ özel durumunu bir iş parçacığından diğerine taşır.

```cpp
// transport_exception.cpp
// compile with: /EHsc /MD
#include <windows.h>
#include <stdio.h>
#include <exception>
#include <stdexcept>

using namespace std;

// Define thread-specific information.
#define THREADCOUNT 2
exception_ptr aException[THREADCOUNT];
int           aArg[THREADCOUNT];

DWORD WINAPI ThrowExceptions( LPVOID );

// Specify a user-defined, custom exception.
// As a best practice, derive your exception
// directly or indirectly from std::exception.
class myException : public std::exception {
};
int main()
{
    HANDLE aThread[THREADCOUNT];
    DWORD ThreadID;

    // Create secondary threads.
    for( int i=0; i < THREADCOUNT; i++ )
    {
        aArg[i] = i;
        aThread[i] = CreateThread(
            NULL,       // Default security attributes.
            0,          // Default stack size.
            (LPTHREAD_START_ROUTINE) ThrowExceptions,
            (LPVOID) &aArg[i], // Thread function argument.
            0,          // Default creation flags.
            &ThreadID); // Receives thread identifier.
        if( aThread[i] == NULL )
        {
            printf("CreateThread error: %d\n", GetLastError());
            return -1;
        }
    }

    // Wait for all threads to terminate.
    WaitForMultipleObjects(THREADCOUNT, aThread, TRUE, INFINITE);
    // Close thread handles.
    for( int i=0; i < THREADCOUNT; i++ ) {
        CloseHandle(aThread[i]);
    }

    // Rethrow and catch the transported exceptions.
    for ( int i = 0; i < THREADCOUNT; i++ ) {
        try {
            if (aException[i] == NULL) {
                printf("exception_ptr %d: No exception was transported.\n", i);
            }
            else {
                rethrow_exception( aException[i] );
            }
        }
        catch( const invalid_argument & ) {
            printf("exception_ptr %d: Caught an invalid_argument exception.\n", i);
        }
        catch( const myException & ) {
            printf("exception_ptr %d: Caught a  myException exception.\n", i);
        }
    }
}
// Each thread throws an exception depending on its thread
// function argument, and then ends.
DWORD WINAPI ThrowExceptions( LPVOID lpParam )
{
    int x = *((int*)lpParam);
    if (x == 0) {
        try {
            // Standard C++ exception.
            // This example explicitly throws invalid_argument exception.
            // In practice, your application performs an operation that
            // implicitly throws an exception.
            throw invalid_argument("A C++ exception.");
        }
        catch ( const invalid_argument & ) {
            aException[x] = current_exception();
        }
    }
    else {
        // User-defined exception.
        aException[x] = make_exception_ptr( myException() );
    }
    return TRUE;
}
```

```Output
exception_ptr 0: Caught an invalid_argument exception.
exception_ptr 1: Caught a  myException exception.
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<özel durum >

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)<br/>
[/EH (Özel Durum İşleme Modeli)](../build/reference/eh-exception-handling-model.md)<br/>
[/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)
