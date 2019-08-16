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
ms.openlocfilehash: db9546bb02fcd5b253fec29777fd71172e50739e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500596"
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
|*Memesi*|`exception_ptr` Türü uygulamak için kullanılan belirtilmemiş bir iç sınıf.|
|*p*|Özel `exception_ptr` duruma başvuran bir nesne.|
|*E*|Bir özel durumu temsil eden sınıf.|
|*e*|Parametre `E` sınıfının bir örneği.|

## <a name="return-value"></a>Dönüş Değeri

İşlevi, devam etmekte `exception_ptr` olan özel duruma başvuran bir nesne döndürür. `current_exception` Devam eden bir özel durum yoksa, işlev herhangi bir özel `exception_ptr` durumla ilişkilendirilmemiş bir nesne döndürür.

İşlevi, e parametresi `exception_ptr` tarafından belirtilen özel duruma başvuran bir nesne döndürür. `make_exception_ptr`

## <a name="remarks"></a>Açıklamalar

### <a name="scenario"></a>Senaryo

Bir değişkenin çalışma miktarını işleyebilmek için ölçeklenebilen bir uygulama oluşturmak istediğinizi düşünün. Bunu gerçekleştirmek için çok iş parçacıklı bir uygulama tasarlayın; bu uygulamada ilk, birincil iş parçacığı işi yapmak için gereken sayıda ikincil iş parçacığını oluşturur. İkincil iş parçacıkları yükleri dengelemek, verimi artırmak ve kaynakları yönetmek için birincil iş parçacıklarına yardımcı olur. İşi dağıtarak, çok iş parçacıklı uygulamalar tek iş parçacıklı uygulamalardan daha iyi performans gösterir.

Ancak, ikincil bir iş parçacığı bir özel durum oluşturursa, birincil iş parçacığının bu durumu işlemesini istersiniz. Bunun nedeni, ikincil iş parçacığı sayısı ne olursa olsun uygulamanızın tutarlı ve birleştirilmiş bir şekilde özel durumları işlemesini istemenizdir.

### <a name="solution"></a>Çözüm

C++ Standard, önceki senaryonun işlenmesi için, bir özel durumun iş parçacıkları arasında taşınmasını destekler. İkincil bir iş parçacığı bir özel durum oluşturursa, bu özel durum *geçerli özel durum*olur. Benzerleme vurguladı ile gerçek dünyaya, geçerli özel durumun *uçuş*aşamasında olduğu söylenir. Geçerli özel durum, özel durum işleyicisi tarafından dönüşü yakalanana kadar uçuştadır.

İkincil iş parçacığı, bir **catch** bloğunda geçerli özel durumu yakalayabilir ve sonra özel durumu bir `current_exception` `exception_ptr` nesne içinde depolamak için işlevini çağırabilir. `exception_ptr` Nesne, ikincil iş parçacığı ve birincil iş parçacığı için kullanılabilir olmalıdır. Örneğin, `exception_ptr` nesnesi, erişimi bir mutex tarafından denetlenen genel bir değişken olabilir. *Özel durum taşıma* terimi, bir iş parçacığında bir özel durumun başka bir iş parçacığı tarafından erişilebilen bir biçime dönüştürülebileceği anlamına gelir.

Ardından, birincil iş parçacığı `rethrow_exception` işlevini çağırarak `exception_ptr` nesnesinden özel durumu ayıklar ve sonra oluşturur. Özel durum oluştuğunda, birincil iş parçacığındaki geçerli özel durum haline gelir. Diğer bir deyişle, özel durum birincil iş parçacığında oluşmuş görünür.

Son olarak, birincil iş parçacığı geçerli özel durumu bir **catch** bloğunda yakalayabilir ve sonra işleyebilir veya daha yüksek düzeydeki bir özel durum işleyicisine atar. Ya da birincil iş parçacığı özel durumu yoksayar ve işlemi sonlandırmaya izin verir.

Çoğu uygulamada özel durumların iş parçacıkları arasında taşınması gerekmez. Ancak, sistem işi ikincil iş parçacıkları, işlemci veya çekirdek arasında bölebildiğinden, bu özellik paralel bir bilgi işlem sisteminde yararlıdır. Paralel bir bilgi işlem ortamında, tek ve özel bir iş parçacığı ikincil iş parçacıklarından gelen tüm özel durumları işleyebilir ve herhangi bir uygulama için tutarlı bir özel durum işleme modeli sunabilir.

C++ Standartları komitesi teklifi hakkında daha fazla bilgi için, internette "Özel Durumları İş Parçacıkları Arasında Taşıma için Dil Desteği" başlıklı N2179 belge numarasını arayın.

### <a name="exception-handling-models-and-compiler-options"></a>Özel Durum-İşleme Modelleri ve Derleyici Seçenekleri

Uygulamanızın özel durum işleme modeli, bir özel durumu yakalayıp taşıyabileceğini ya da bunu yapamayacağınızı belirler. Visual C+; C++ özel durumlarını, yapılandırılmış özel durum işleme (SEH) özel durumlarını ve ortak dil çalışma zamanı (CLR) özel durumlarını işleyebilen üç modeli destekler. Uygulamanızın özel durum işleme modelini belirtmek için [/Eh](../build/reference/eh-exception-handling-model.md) ve [/clr](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneklerini kullanın.

Yalnızca aşağıdaki derleyici seçeneklerinin ve programlama deyimlerinin birleşimi bir özel durumu taşıyabilir. Diğer birleşimler özel durumları yakalayamaz ya da özel durumları yakalasa da taşıyamaz.

- **/EHa** derleyici seçeneği ve **catch** deyimleri, SEH ve C++ özel durumları taşıyabilir.

- **/EHa**, **/EHS**ve **/EHsc** derleyici seçenekleri ve **catch** deyimleri C++ özel durumları taşıyabilir.

- **/Clr** derleyici seçeneği ve **catch** deyimleri C++ özel durumları taşıyabilir. **/Clr** derleyici seçeneği, **/EHa** seçeneğinin belirtimini gerektirir. Derleyicinin yönetilen özel durumların taşınmasını desteklemediğini unutmayın. Bunun nedeni, [System. Exception sınıfından](../standard-library/exception-class.md)türetilen yönetilen özel durumların, ortak dil çalışma zamanının tesislerini kullanarak iş parçacıkları arasında taşıyabildiğiniz bir nesnelerdir.

   > [!IMPORTANT]
   > **/EHsc** derleyici seçeneğini belirtmenizi ve yalnızca C++ özel durumları yakalanmasını öneririz. **/EHa** veya **/clr** derleyici seçeneğini ve üç nokta *özel durum bildirimi* (`catch(...)`) ile bir **catch** bildirimini kullanırsanız, kendinizi bir güvenlik tehditlerine maruz olursunuz. Büyük olasılıkla bazı özel durumları yakalamak için **catch** ifadesini kullanmayı amaçlarsınız. Ancak, `catch(...)` ifade, önemli olması C++ gereken beklenmeyen olanlar da dahil olmak üzere All ve SEH özel durumlarını yakalar. Beklenmeyen bir özel durumu yoksayarsanız ya da düzgün işleyemezseniz, kötü amaçlı yazılımlar programınızın güvenliğine zarar vermek için bu fırsatı kullanabilir.

## <a name="usage"></a>Kullanım

Aşağıdaki bölümlerde, `exception_ptr` türü `current_exception`ve, `rethrow_exception`ve `make_exception_ptr` işlevleri kullanılarak özel durumların nasıl taşınması anlatılmaktadır.

## <a name="exception_ptr-type"></a>exception_ptr Türü

Geçerli özel `exception_ptr` duruma veya Kullanıcı tarafından belirtilen özel durum örneğine başvurmak için bir nesne kullanın. Microsoft uygulamasında bir özel durum, bir [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) yapısı tarafından temsil edilir. Her `exception_ptr` nesne, özel durumu temsil eden `EXCEPTION_RECORD` yapının bir kopyasına işaret eden bir özel durum başvurusu alanı içerir.

Bir `exception_ptr` değişken bildirdiğinizde, değişken herhangi bir özel durumla ilişkili değildir. Diğer bir deyişle, özel durum başvuru alanı NULL olur. Böyle bir nesne null exception_ptr olarak adlandırılır. `exception_ptr`

`current_exception` Bir `make_exception_ptr` nesneye özel durumatamakiçinorişlevinikullanın.`exception_ptr` Bir `exception_ptr` değişkene bir özel durum atadığınızda, değişkenin özel durum başvuru alanı özel durumun bir kopyasına işaret eder. Özel durumu kopyalamak için yeterli bellek yoksa, özel durum başvuru alanı bir [std:: bad_alloc](../standard-library/bad-alloc-class.md) özel durumunun kopyasına işaret eder. OR işlevi başka bir nedenle özel durumu kopyalayamayacağı takdirde, işlev geçerli işlemden çıkmak için Terminate işlevini çağırır. [](../c-runtime-library/reference/terminate-crt.md) `current_exception` `make_exception_ptr`

Adına rağmen bir `exception_ptr` nesne bir işaretçi değildir. İşaretçi semantiğini etkilemez ve işaretçi üye erişimi (`->`) veya yöneltme (`*`) işleçleriyle kullanılamaz. `exception_ptr` Nesnenin ortak veri üyeleri veya üye işlevleri yok.

### <a name="comparisons"></a>Karşılaştırma

İki`!=``==` nesneyikarşılaştırmakiçineşittir()veNot-eşit()işleçlerinikullanabilirsiniz.`exception_ptr` İşleçler, özel durumları temsil eden `EXCEPTION_RECORD` yapıların ikili değerini (bit düzeniyle) karşılaştırmaz. Bunun yerine, işleçler, `exception_ptr` nesnelerin özel durum başvurusu alanındaki adresleri karşılaştırır. Sonuç olarak, null `exception_ptr` ve null değeri eşit olarak karşılaştırılır.

## <a name="current_exception-function"></a>current_exception İşlevi

Bir **catch** bloğunda işlevi`current_exception` çağırın. Bir özel durum uçuş durumunda ve **catch** bloğu özel durumu yakalayabiliyorsanız, `current_exception` işlev özel duruma başvuran bir `exception_ptr` nesne döndürür. Aksi takdirde, işlev null `exception_ptr` bir nesne döndürür.

### <a name="details"></a>Ayrıntılar

İşlevi, catch ifadesinin bir [özel durum bildirimi](../cpp/try-throw-and-catch-statements-cpp.md) bildirimi belirttiğinden bağımsız olarak, uçuştaki özel durumu yakalar. `current_exception`

Özel durumu yeniden oluşturmazsınız, geçerli özel durum için yok edici **catch** bloğunun sonunda çağırılır. Ancak, `current_exception` işlevi yıkıcıda çağırsanız bile, işlev geçerli özel duruma başvuran bir `exception_ptr` nesne döndürür.

`current_exception` İşleve art arda yapılan çağrılar, `exception_ptr` geçerli özel durumun farklı kopyalarına başvuran nesneler döndürür. Sonuç olarak, kopyalar aynı ikili değerde olsalar da farklı kopyalara başvurduklarından, nesneler eşit olmayarak karşılaştırılır.

### <a name="seh-exceptions"></a>SEH özel durumları

**/EHa** derleyici seçeneğini kullanırsanız, bir C++ SEH özel durumunu **catch** bloğunda yakalayabilirsiniz. İşlevi, SEH özel `exception_ptr` durumuna başvuran bir nesne döndürür. `current_exception` Ve işlevi bağımsız değişkeni olarak thetranted `exception_ptr` nesnesiyle birlikte çağırırsanız, SEH özel durumunu atar. `rethrow_exception`

`exception_ptr` İşlevi bir SEH __finally sonlandırma işleyicisine, bir __except özel durum işleyicisine veya __except filtre ifadesine çağırırsanız null değeri döndürür. `current_exception`

Taşınan özel durumlar iç içe geçmiş özel durumları desteklemez. Bir iç içe geçmiş özel durum, bir özel durum işlenirken başka bir özel durumun oluşturulmasıyla ortaya çıkar. İç içe geçmiş bir özel durumu yakalarsanız `EXCEPTION_RECORD.ExceptionRecord` , veri üyesi ilişkili özel durumları tanımlayan `EXCEPTION_RECORD` bir yapı zincirine işaret eder. İşlevi `current_exception` , `ExceptionRecord` veri üyesi sıfırlandı bir `exception_ptr` nesne döndürdüğünden iç içe özel durumları desteklemez.

Bir seh özel durumu yakalarsanız, `EXCEPTION_RECORD.ExceptionInformation` veri üyesi dizisindeki herhangi bir işaretçi tarafından başvurulan belleği yönetmeniz gerekir. Belleğin, karşılık gelen `exception_ptr` nesnenin ömrü boyunca geçerli olduğunu ve `exception_ptr` nesne silindiğinde belleğin serbest olduğunu garanti etmeniz gerekir.

Yapılandırılmış özel durum (SE) çevirici işlevlerini özel durumları taşıma özelliğiyle birlikte kullanabilirsiniz. Bir seh özel durumu bir C++ özel duruma çevrilmişse, `current_exception` işlev özgün SEH özel durumu yerine çevrilmiş özel duruma başvuran bir `exception_ptr` döndürür. `rethrow_exception` İşlev daha sonra, özgün özel durum değil, çevrilmiş özel durumu oluşturur. İ çevirici işlevleri hakkında daha fazla bilgi için bkz. [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).

## <a name="rethrow_exception-function"></a>rethrow_exception İşlevi

Bir `exception_ptr` nesnede yakalanan bir özel durum depoladıktan sonra, birincil iş parçacığı nesneyi işleyebilir. Birincil iş parçacığın bağımsız değişkeni olarak `rethrow_exception` `exception_ptr` nesnesiyle birlikte işlevi çağırın. `rethrow_exception` İşlevi `exception_ptr` nesnesinden özel durumu ayıklar ve ardından birincil iş parçacığı bağlamında özel durumu oluşturur. `rethrow_exception` İşlevin *p* parametresi null `exception_ptr`ise, işlev [std:: bad_exception](../standard-library/bad-exception-class.md)atar.

Ayıklanan özel durum artık birincil iş parçacığında geçerli özel durumdur ve diğer özel durumlar gibi onu işleyebilirsiniz. Özel durumu yakalarsanız, hemen işleyebilir veya bir **throw** ifadesini kullanarak daha yüksek düzey özel durum işleyicisine gönderebilirsiniz. Aksi halde, hiçbir şey yapmayın ve varsayılan sistem özel durum işleyicisinin işlemi sonlandırmasına izin verin.

## <a name="make_exception_ptr-function"></a>make_exception_ptr İşlevi

İşlevi, bağımsız değişkeni olarak bir sınıfın örneğini alır ve sonra örneğe başvuran bir `exception_ptr` döndürür. `make_exception_ptr` Genellikle, `make_exception_ptr` işlev bağımsız değişkeni olarak bir [özel durum sınıfı](../standard-library/exception-class.md) nesnesi belirtirsiniz, ancak herhangi bir sınıf nesnesi bağımsız değişken olabilir.

C++ `current_exception` `exception_ptr` İşlevi çağırmak, özel durum atma, bir catch bloğunda yakalama ve sonra özel duruma başvuran bir nesne döndürmek için işlevini çağırma ile eşdeğerdir. `make_exception_ptr` `make_exception_ptr` İşlevin Microsoft uygulamasında uygulanması daha etkilidir ve bir özel durum yakalanmasıdır.

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
