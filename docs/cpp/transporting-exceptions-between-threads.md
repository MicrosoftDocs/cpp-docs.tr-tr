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
ms.openlocfilehash: 1b3e6ffa0e98d54b047e18e4c023a8f5173470b1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186106"
---
# <a name="transporting-exceptions-between-threads"></a>Özel durumları iş parçacıkları arasında taşıma

Microsoft C++ derleyicisi (MSVC) bir *özel durumun* bir iş parçacığından diğerine taşınmasını destekler. Taşınan özel durumlar bir iş parçacığındaki özel durumu yakalamanızı sağlar ve sonra özel durumun farklı bir iş parçacığında oluşmuş gibi görünmesini sağlar. Örneğin, bu özelliği birincil iş parçacığının ikincil iş parçacıkları tarafından oluşturulan tüm özel durumları işlediği çok iş parçacıklı bir uygulamayı yazmak için kullanabilirsiniz. Özel durum taşımaları, çoğunlukla paralel programlama kitaplıkları veya sistemleri oluşturan geliştiriciler için yararlıdır. MSVC, taşıma özel durumlarını uygulamak için [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) türünü ve [current_exception](../standard-library/exception-functions.md#current_exception), [rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)ve [make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr) işlevlerini sağlar.

## <a name="syntax"></a>Söz dizimi

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
|*Memesi*|Türü uygulamak için kullanılan belirtilmemiş bir iç sınıf `exception_ptr` .|
|*Lama*|`exception_ptr`Özel duruma başvuran bir nesne.|
|*A*|Bir özel durumu temsil eden sınıf.|
|*a*|Parametre sınıfının bir örneği `E` .|

## <a name="return-value"></a>Döndürülen değer

`current_exception`İşlevi, `exception_ptr` devam etmekte olan özel duruma başvuran bir nesne döndürür. Devam eden bir özel durum yoksa, işlev `exception_ptr` herhangi bir özel durumla ilişkilendirilmemiş bir nesne döndürür.

`make_exception_ptr`İşlevi, `exception_ptr` *e* parametresi tarafından belirtilen özel duruma başvuran bir nesne döndürür.

## <a name="remarks"></a>Açıklamalar

### <a name="scenario"></a>Senaryo

Bir değişkenin çalışma miktarını işleyebilmek için ölçeklenebilen bir uygulama oluşturmak istediğinizi düşünün. Bunu gerçekleştirmek için çok iş parçacıklı bir uygulama tasarlayın; bu uygulamada ilk, birincil iş parçacığı işi yapmak için gereken sayıda ikincil iş parçacığını oluşturur. İkincil iş parçacıkları yükleri dengelemek, verimi artırmak ve kaynakları yönetmek için birincil iş parçacıklarına yardımcı olur. İşi dağıtarak, çok iş parçacıklı uygulamalar tek iş parçacıklı uygulamalardan daha iyi performans gösterir.

Ancak, ikincil bir iş parçacığı bir özel durum oluşturursa, birincil iş parçacığının bu durumu işlemesini istersiniz. Bunun nedeni, ikincil iş parçacığı sayısı ne olursa olsun uygulamanızın tutarlı ve birleştirilmiş bir şekilde özel durumları işlemesini istemenizdir.

### <a name="solution"></a>Çözüm

C++ Standard, önceki senaryonun işlenmesi için, bir özel durumun iş parçacıkları arasında taşınmasını destekler. İkincil bir iş parçacığı bir özel durum oluşturursa, bu özel durum *geçerli özel durum*olur. Benzerleme vurguladı ile gerçek dünyaya, geçerli özel durumun *uçuş*aşamasında olduğu söylenir. Geçerli özel durum, özel durum işleyicisi tarafından dönüşü yakalanana kadar uçuştadır.

İkincil iş parçacığı, geçerli özel durumu bir blokta yakalayabilir **`catch`** ve sonra `current_exception` özel durumu bir nesne içinde depolamak için işlevini çağırır `exception_ptr` . `exception_ptr`Nesne, ikincil iş parçacığı ve birincil iş parçacığı için kullanılabilir olmalıdır. Örneğin, nesnesi, `exception_ptr` erişimi bir mutex tarafından denetlenen genel bir değişken olabilir. *Özel durum taşıma* terimi, bir iş parçacığında bir özel durumun başka bir iş parçacığı tarafından erişilebilen bir biçime dönüştürülebileceği anlamına gelir.

Ardından, birincil iş parçacığı işlevini çağırarak `rethrow_exception` nesnesinden özel durumu ayıklar ve sonra oluşturur `exception_ptr` . Özel durum oluştuğunda, birincil iş parçacığındaki geçerli özel durum haline gelir. Diğer bir deyişle, özel durum birincil iş parçacığında oluşmuş görünür.

Son olarak, birincil iş parçacığı geçerli özel durumu bir blokta yakalayabilir **`catch`** ve sonra işleyebilir veya daha yüksek düzeydeki bir özel durum işleyicisine atar. Ya da birincil iş parçacığı özel durumu yoksayar ve işlemi sonlandırmaya izin verir.

Çoğu uygulamada özel durumların iş parçacıkları arasında taşınması gerekmez. Ancak, sistem işi ikincil iş parçacıkları, işlemci veya çekirdek arasında bölebildiğinden, bu özellik paralel bir bilgi işlem sisteminde yararlıdır. Paralel bir bilgi işlem ortamında, tek ve özel bir iş parçacığı ikincil iş parçacıklarından gelen tüm özel durumları işleyebilir ve herhangi bir uygulama için tutarlı bir özel durum işleme modeli sunabilir.

C++ Standartları komitesi teklifi hakkında daha fazla bilgi için, internette "Özel Durumları İş Parçacıkları Arasında Taşıma için Dil Desteği" başlıklı N2179 belge numarasını arayın.

### <a name="exception-handling-models-and-compiler-options"></a>Özel durum işleme modelleri ve derleyici seçenekleri

Uygulamanızın özel durum işleme modeli, bir özel durumu yakalayıp taşıyabileceğini ya da bunu yapamayacağınızı belirler. Visual C+; C++ özel durumlarını, yapılandırılmış özel durum işleme (SEH) özel durumlarını ve ortak dil çalışma zamanı (CLR) özel durumlarını işleyebilen üç modeli destekler. Uygulamanızın özel durum işleme modelini belirtmek için [/Eh](../build/reference/eh-exception-handling-model.md) ve [/clr](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneklerini kullanın.

Yalnızca aşağıdaki derleyici seçeneklerinin ve programlama deyimlerinin birleşimi bir özel durumu taşıyabilir. Diğer birleşimler özel durumları yakalayamaz ya da özel durumları yakalasa da taşıyamaz.

- **/EHa** derleyici seçeneği ve DEYIMLERI, **`catch`** SEH ve C++ özel durumlarını taşıyabilir.

- **/EHa**, **/EHS**ve **/EHsc** derleyici seçenekleri ve **`catch`** deyimleri, C++ özel durumlarını taşıyabilir.

- **/Clr** derleyici seçeneği ve deyimleri, **`catch`** C++ özel durumlarını taşıyabilir. **/Clr** derleyici seçeneği, **/EHa** seçeneğinin belirtimini gerektirir. Derleyicinin yönetilen özel durumların taşınmasını desteklemediğini unutmayın. Bunun nedeni, [System. Exception sınıfından](../standard-library/exception-class.md)türetilen yönetilen özel durumların, ortak dil çalışma zamanının tesislerini kullanarak iş parçacıkları arasında taşıyabildiğiniz bir nesnelerdir.

   > [!IMPORTANT]
   > **/EHsc** derleyici seçeneğini belirtmenizi ve yalnızca C++ özel durumlarını yakalanmasını öneririz. **/EHa** veya **/clr** derleyici seçeneğini kullanırsanız ve **`catch`** üç nokta *özel durum bildirimi* () içeren bir ifade kullanıyorsanız kendinizi bir güvenlik tehditlerine sunun `catch(...)` . Büyük olasılıkla **`catch`** bazı özel durumları yakalamak için ifadesini kullanmayı amaçlarsınız. Ancak, `catch(...)` ifade, önemli olması gereken beklenmeyen olanlar da dahil olmak üzere tüm C++ ve SEH özel durumlarını yakalar. Beklenmeyen bir özel durumu yoksayarsanız ya da düzgün işleyemezseniz, kötü amaçlı yazılımlar programınızın güvenliğine zarar vermek için bu fırsatı kullanabilir.

## <a name="usage"></a>Kullanım

Aşağıdaki bölümlerde, `exception_ptr` türü ve `current_exception` , `rethrow_exception` ve işlevleri kullanılarak özel durumların nasıl taşınması anlatılmaktadır `make_exception_ptr` .

## <a name="exception_ptr-type"></a>exception_ptr türü

`exception_ptr`Geçerli özel duruma veya Kullanıcı tarafından belirtilen özel durum örneğine başvurmak için bir nesne kullanın. Microsoft uygulamasında bir özel durum [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) yapısıyla temsil edilir. Her `exception_ptr` nesne `EXCEPTION_RECORD` , özel durumu temsil eden yapının bir kopyasına işaret eden bir özel durum başvurusu alanı içerir.

Bir `exception_ptr` değişken bildirdiğinizde, değişken herhangi bir özel durumla ilişkili değildir. Diğer bir deyişle, özel durum başvuru alanı NULL olur. Böyle bir `exception_ptr` nesne *null exception_ptr*olarak adlandırılır.

`current_exception` `make_exception_ptr` Bir nesneye özel durum atamak için or işlevini kullanın `exception_ptr` . Bir değişkene bir özel durum atadığınızda `exception_ptr` , değişkenin özel durum başvuru alanı özel durumun bir kopyasına işaret eder. Özel durumu kopyalamak için yeterli bellek yoksa, özel durum başvuru alanı bir [std:: bad_alloc](../standard-library/bad-alloc-class.md) özel durumunun kopyasına işaret eder. `current_exception`Or `make_exception_ptr` işlevi başka bir nedenle özel durumu kopyalayamayacağı takdirde, işlev geçerli işlemden çıkmak için [Terminate](../c-runtime-library/reference/terminate-crt.md) işlevini çağırır.

Adına rağmen bir `exception_ptr` nesne bir işaretçi değildir. İşaretçi semantiğini etkilemez ve işaretçi üye erişimi ( `->` ) veya yöneltme ( `*` ) işleçleriyle kullanılamaz. `exception_ptr`Nesnenin ortak veri üyeleri veya üye işlevleri yok.

### <a name="comparisons"></a>Karşılaştırmalar

`==`İki nesneyi karşılaştırmak için eşittir () ve Not-eşit ( `!=` ) işleçlerini kullanabilirsiniz `exception_ptr` . İşleçler, `EXCEPTION_RECORD` özel durumları temsil eden yapıların ikili değerini (bit düzeniyle) karşılaştırmaz. Bunun yerine, işleçler, nesnelerin özel durum başvurusu alanındaki adresleri karşılaştırır `exception_ptr` . Sonuç olarak, null `exception_ptr` ve null değeri eşit olarak karşılaştırılır.

## <a name="current_exception-function"></a>current_exception işlevi

`current_exception`İşlevi bir **`catch`** blokta çağırın. Bir özel durum uçuş durumunda ve **`catch`** blok özel durumu yakalayabiliyorsanız, `current_exception` işlev `exception_ptr` özel duruma başvuran bir nesne döndürür. Aksi takdirde, işlev null bir `exception_ptr` nesne döndürür.

### <a name="details"></a>Ayrıntılar

`current_exception`İşlevi, **`catch`** deyimin bir [özel durum bildirimi](../cpp/try-throw-and-catch-statements-cpp.md) bildirimi belirttiğinden bağımsız olarak, uçuştaki özel durumu yakalar.

Özel durumu yeniden oluşturmayadıysanız, geçerli özel durumun yıkıcısı bloğunun sonunda çağırılır **`catch`** . Ancak, `current_exception` işlevi yıkıcıda çağırsanız bile, işlev `exception_ptr` geçerli özel duruma başvuran bir nesne döndürür.

İşleve art arda yapılan çağrılar `current_exception` `exception_ptr` , geçerli özel durumun farklı kopyalarına başvuran nesneler döndürür. Sonuç olarak, kopyalar aynı ikili değerde olsalar da farklı kopyalara başvurduklarından, nesneler eşit olmayarak karşılaştırılır.

### <a name="seh-exceptions"></a>SEH özel durumları

**/EHa** derleyici seçeneğini kullanırsanız, bir seh özel durumunu C++ **`catch`** bloğunda yakalayabilirsiniz. `current_exception`İşlevi, `exception_ptr` SEH özel durumuna başvuran bir nesne döndürür. Ve `rethrow_exception` işlevi bağımsız değişkeni olarak thetranted nesnesiyle birlikte çağırırsanız, SEH özel durumunu atar `exception_ptr` .

`current_exception`İşlevi BIR `exception_ptr` SEH **`__finally`** sonlandırma işleyicisine, **`__except`** özel durum işleyicisine veya **`__except`** filtre ifadesine çağırırsanız, null değeri döndürür.

Taşınan özel durumlar iç içe geçmiş özel durumları desteklemez. Bir iç içe geçmiş özel durum, bir özel durum işlenirken başka bir özel durumun oluşturulmasıyla ortaya çıkar. İç içe geçmiş bir özel durumu yakalarsanız, `EXCEPTION_RECORD.ExceptionRecord` veri üyesi `EXCEPTION_RECORD` ilişkili özel durumları tanımlayan bir yapı zincirine işaret eder. `current_exception`İşlevi, `exception_ptr` `ExceptionRecord` veri üyesi sıfırlandı bir nesne döndürdüğünden iç içe özel durumları desteklemez.

Bir SEH özel durumu yakalarsanız, veri üyesi dizisindeki herhangi bir işaretçi tarafından başvurulan belleği yönetmeniz gerekir `EXCEPTION_RECORD.ExceptionInformation` . Belleğin, karşılık gelen nesnenin ömrü boyunca geçerli olduğunu `exception_ptr` ve nesne silindiğinde belleğin serbest olduğunu garanti etmeniz gerekir `exception_ptr` .

Yapılandırılmış özel durum (SE) çevirici işlevlerini özel durumları taşıma özelliğiyle birlikte kullanabilirsiniz. Bir SEH özel durumu bir C++ özel durumuna çevrilmişse, `current_exception` işlev `exception_ptr` özgün SEH özel durumu yerine çevrilmiş özel duruma başvuran bir döndürür. `rethrow_exception`İşlev daha sonra, özgün özel durum değil, çevrilmiş özel durumu oluşturur. İ çevirici işlevleri hakkında daha fazla bilgi için bkz. [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).

## <a name="rethrow_exception-function"></a>rethrow_exception işlevi

Bir nesnede yakalanan bir özel durum depoladıktan sonra `exception_ptr` , birincil iş parçacığı nesneyi işleyebilir. Birincil iş parçacığın `rethrow_exception` `exception_ptr` bağımsız değişkeni olarak nesnesiyle birlikte işlevi çağırın. `rethrow_exception`İşlevi nesnesinden özel durumu ayıklar `exception_ptr` ve ardından birincil iş parçacığı bağlamında özel durumu oluşturur. İşlevin *p* parametresi `rethrow_exception` null ise `exception_ptr` , işlev [std:: bad_exception](../standard-library/bad-exception-class.md)oluşturur.

Ayıklanan özel durum artık birincil iş parçacığında geçerli özel durumdur ve diğer özel durumlar gibi onu işleyebilirsiniz. Özel durumu yakalarsanız, hemen işleyebilir veya bir **`throw`** ifade kullanarak daha yüksek düzey özel durum işleyicisine gönderebilirsiniz. Aksi halde, hiçbir şey yapmayın ve varsayılan sistem özel durum işleyicisinin işlemi sonlandırmasına izin verin.

## <a name="make_exception_ptr-function"></a>make_exception_ptr işlevi

`make_exception_ptr`İşlevi, bağımsız değişkeni olarak bir sınıfın örneğini alır ve sonra örneğe başvuran bir döndürür `exception_ptr` . Genellikle, işlev bağımsız değişkeni olarak bir [özel durum sınıfı](../standard-library/exception-class.md) nesnesi belirtirsiniz `make_exception_ptr` , ancak herhangi bir sınıf nesnesi bağımsız değişken olabilir.

İşlevi çağırmak `make_exception_ptr` , bir C++ özel durumu oluşturma, bir **`catch`** blokta yakalama ve sonra `current_exception` özel duruma başvuran bir nesne döndürmek için işlevini çağırma ile eşdeğerdir `exception_ptr` . İşlevin Microsoft uygulamasında uygulanması `make_exception_ptr` daha etkilidir ve bir özel durum yakalanmasıdır.

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

**Üst bilgi:**\<exception>

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)<br/>
[/EH (özel durum Işleme modeli)](../build/reference/eh-exception-handling-model.md)<br/>
[/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)
