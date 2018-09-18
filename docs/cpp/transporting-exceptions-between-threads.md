---
title: Özel durumları iş parçacıkları arasında taşıma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46cdf86d431b69704b5a67fea3024365470de945
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066370"
---
# <a name="transporting-exceptions-between-threads"></a>Özel durumları iş parçacıkları arasında taşıma

Visual C++ destekler *bir özel durum taşıma* bir iş parçacığından diğerine. Taşınan özel durumlar bir iş parçacığındaki özel durumu yakalamanızı sağlar ve sonra özel durumun farklı bir iş parçacığında oluşmuş gibi görünmesini sağlar. Örneğin, bu özelliği birincil iş parçacığının ikincil iş parçacıkları tarafından oluşturulan tüm özel durumları işlediği çok iş parçacıklı bir uygulamayı yazmak için kullanabilirsiniz. Özel durum taşımaları, çoğunlukla paralel programlama kitaplıkları veya sistemleri oluşturan geliştiriciler için yararlıdır. Taşınan özel durumun uygulanması için Visual C++ sağlar [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) türü ve [current_exception](../standard-library/exception-functions.md#current_exception), [rethrow_exception](../standard-library/exception-functions.md#rethrow_exception), ve [make_ exception_ptr](../standard-library/exception-functions.md#make_exception_ptr) işlevleri.

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
|*Belirtilmemiş*|Uygulamak için kullanılan belirtilmemiş bir iç sınıf `exception_ptr` türü.|
|*p*|Bir `exception_ptr` bir özel duruma başvuran bir nesne.|
|*E*|Bir özel durumu temsil eden sınıf.|
|*e*|Parametre örneği `E` sınıfı.|

## <a name="return-value"></a>Dönüş Değeri

`current_exception` İşlevinin döndürdükleriyle bir `exception_ptr` şu anda sürmekte olan özel duruma başvuran bir nesne. Hiçbir özel durum sürmüyorsa, işlev döndürür bir `exception_ptr` nesnesini herhangi bir özel durumla ilişkili değildir.

`make_exception_ptr` İşlevinin döndürdükleriyle bir `exception_ptr` tarafından belirtilen özel duruma başvuran nesne *e* parametresi.

## <a name="remarks"></a>Açıklamalar

### <a name="scenario"></a>Senaryo

Bir değişkenin çalışma miktarını işleyebilmek için ölçeklenebilen bir uygulama oluşturmak istediğinizi düşünün. Bunu gerçekleştirmek için çok iş parçacıklı bir uygulama tasarlayın; bu uygulamada ilk, birincil iş parçacığı işi yapmak için gereken sayıda ikincil iş parçacığını oluşturur. İkincil iş parçacıkları yükleri dengelemek, verimi artırmak ve kaynakları yönetmek için birincil iş parçacıklarına yardımcı olur. İşi dağıtarak, çok iş parçacıklı uygulamalar tek iş parçacıklı uygulamalardan daha iyi performans gösterir.

Ancak, ikincil bir iş parçacığı bir özel durum oluşturursa, birincil iş parçacığının bu durumu işlemesini istersiniz. Bunun nedeni, ikincil iş parçacığı sayısı ne olursa olsun uygulamanızın tutarlı ve birleştirilmiş bir şekilde özel durumları işlemesini istemenizdir.

### <a name="solution"></a>Çözüm

C++ Standard, önceki senaryonun işlenmesi için, bir özel durumun iş parçacıkları arasında taşınmasını destekler. İkincil bir iş parçacığı bir özel durum oluşturursa, bu özel durum haline gelir *geçerli özel durumun*. Gerçek dünyaya benzerliği tarafından geçerli özel durumun olduğu söylenir *uçuştaki*. Geçerli özel durum, özel durum işleyicisi tarafından dönüşü yakalanana kadar uçuştadır.

İkincil iş parçacığı geçerli özel durum yakalamak bir **catch** engelleme ve sonra çağrı `current_exception` işlev özel durum depolamak için bir `exception_ptr` nesne. `exception_ptr` Nesnesi İkincil iş parçacığı ve birincil iş parçacığı için kullanılabilir olmalıdır. Örneğin, `exception_ptr` nesnesi erişimi bir mutex tarafından denetlenen bir genel değişken olabilir. Terim *bir özel durum taşıma* bir iş parçacığındaki bir özel durum, başka bir iş parçacığı tarafından erişilebilir bir biçime dönüştürülebileceği anlamına gelir.

Ardından, birincil iş parçacığı çağrı `rethrow_exception` ayıklar ve ardından özel durumu oluşturur, işlev `exception_ptr` nesne. Özel durum oluştuğunda, birincil iş parçacığındaki geçerli özel durum haline gelir. Diğer bir deyişle, özel durum birincil iş parçacığında oluşmuş görünür.

Son olarak, birincil iş parçacığı geçerli özel durum yakalayabilir bir **catch** engelleme işleyin veya bir daha yüksek düzeydeki bir özel durum işleyicisine atar. Ya da birincil iş parçacığı özel durumu yoksayar ve işlemi sonlandırmaya izin verir.

Çoğu uygulamada özel durumların iş parçacıkları arasında taşınması gerekmez. Ancak, sistem işi ikincil iş parçacıkları, işlemci veya çekirdek arasında bölebildiğinden, bu özellik paralel bir bilgi işlem sisteminde yararlıdır. Paralel bir bilgi işlem ortamında, tek ve özel bir iş parçacığı ikincil iş parçacıklarından gelen tüm özel durumları işleyebilir ve herhangi bir uygulama için tutarlı bir özel durum işleme modeli sunabilir.

C++ Standartları komitesi teklifi hakkında daha fazla bilgi için, internette "Özel Durumları İş Parçacıkları Arasında Taşıma için Dil Desteği" başlıklı N2179 belge numarasını arayın.

### <a name="exception-handling-models-and-compiler-options"></a>Özel Durum-İşleme Modelleri ve Derleyici Seçenekleri

Uygulamanızın özel durum işleme modeli, bir özel durumu yakalayıp taşıyabileceğini ya da bunu yapamayacağınızı belirler. Visual C+; C++ özel durumlarını, yapılandırılmış özel durum işleme (SEH) özel durumlarını ve ortak dil çalışma zamanı (CLR) özel durumlarını işleyebilen üç modeli destekler. Kullanım [/EH](../build/reference/eh-exception-handling-model.md) ve [/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçenekleri, uygulamanızın özel durum işleme modelini belirtmek için.

Yalnızca aşağıdaki derleyici seçeneklerinin ve programlama deyimlerinin birleşimi bir özel durumu taşıyabilir. Diğer birleşimler özel durumları yakalayamaz ya da özel durumları yakalasa da taşıyamaz.

- **/Eha** derleyici seçeneği ve **catch** deyimi, SEH ve C++ özel durumlarını taşıyabilir.

- **/Eha**, **EHS**, ve **/ehsc** derleyici seçenekleri ve **catch** deyimi, C++ özel durumlarını taşıyabilir.

- **/CLR** derleyici seçeneği ve **catch** deyimi, C++ özel durumlarını taşıyabilir. **/CLR** derleyici seçeneği gelir belirtimi **/eha** seçeneği. Derleyicinin yönetilen özel durumların taşınmasını desteklemediğini unutmayın. Bunun nedeni yönetilen öğesinden türetilen özel durumları, [System.Exception sınıfı](../standard-library/exception-class.md), zaten ortak taşınabilen çalışma zamanı Özellikleri'ni kullanarak iş parçacıkları arasında taşıma nesnelerdir.

   > [!IMPORTANT]
   > Belirttiğiniz öneririz **/ehsc** derleyici seçeneği ve yalnızca C++ özel durumlarını yakalama. Kullanırsanız, kendinizi bir güvenlik tehdidine kullanıma **/eha** veya **/CLR** derleyici seçeneği ve **catch** üç nokta deyimiyle  *özel durum bildirimi* (`catch(...)`). Büyük olasılıkla kullanmayı planlıyorsanız **catch** birkaç belirli özel durumları yakalamak için deyimi. Ancak, `catch(...)` deyimi, önemli beklenmeyen olanlar da dahil olmak üzere tüm C++ ve SEH özel durumları, yakalar. Beklenmeyen bir özel durumu yoksayarsanız ya da düzgün işleyemezseniz, kötü amaçlı yazılımlar programınızın güvenliğine zarar vermek için bu fırsatı kullanabilir.

## <a name="usage"></a>Kullanım

Aşağıdaki bölümlerde kullanarak özel durumları taşıma nasıl `exception_ptr` türü ve `current_exception`, `rethrow_exception`, ve `make_exception_ptr` işlevleri.

## <a name="exceptionptr-type"></a>exception_ptr Türü

Kullanım bir `exception_ptr` geçerli özel durumu veya bir kullanıcı tarafından belirtilen özel durum örneği başvurmak için nesne. Microsoft uygulamasında, bir özel durum tarafından temsil edilen bir [exceptıon_record](/windows/desktop/api/winnt/ns-winnt-_exception_record) yapısı. Her `exception_ptr` nesne içeren bir kopyasına işaret eden bir özel durum başvuru alanı `EXCEPTION_RECORD` özel durumu temsil eden yapısı.

Bildirdiğinizde bir `exception_ptr` değişken, değişken herhangi bir özel durumla ilişkili değil. Diğer bir deyişle, özel durum başvuru alanı NULL olur. Böyle bir `exception_ptr` nesnesinin bir *null exception_ptr*.

Kullanım `current_exception` veya `make_exception_ptr` işlevi için bir özel durum atamak için bir `exception_ptr` nesne. Bir özel durum atadığınızda bir `exception_ptr` değişken, değişkenin özel durum başvuru alanı özel durumun kopyasını gösterir. Özel durum başvuru alanı özel durumu kopyalamak için yeterli bellek varsa, bir kopyasına işaret eden bir [std::bad_alloc](../standard-library/bad-alloc-class.md) özel durum. Varsa `current_exception` veya `make_exception_ptr` işlevi, özel durumun başka bir nedenle, işlev çağrıları kopyalayamıyor [sonlandırmak](../c-runtime-library/reference/terminate-crt.md) geçerli işlemden çıkmak için işlevi.

Adına rağmen bir `exception_ptr` nesnesinin kendisi bir işaretçi değildir. İşaretçi semantiğine uymaz ve işaretçi üye erişimi ile birlikte kullanılamaz (`->`) veya yöneltme (`*`) işleçleri. `exception_ptr` Nesnenin ortak veri üyeleri ya da üye işlevleri vardır.

### <a name="comparisons"></a>Karşılaştırma

Eşit kullanabilirsiniz (`==`) ve eşit değil (`!=`) karşılaştırmak için işleçleri `exception_ptr` nesneleri. İşleçler ikili değerini (bit deseni) karşılaştırın değil `EXCEPTION_RECORD` özel durumları temsil eden yapılar. Bunun yerine, işleçler özel durum başvuru alanlarındaki adresleri karşılaştırır `exception_ptr` nesneleri. Sonuç olarak, bir null `exception_ptr` ve NULL değeri eşit olarak karşılaştırılır.

## <a name="currentexception-function"></a>current_exception İşlevi

Çağrı `current_exception` işlevi bir **catch** blok. Bir özel durum uçuştaysa ve **catch** bloğu özel durumu yakalayabiliyorsa `current_exception` işlevinin döndürdükleriyle bir `exception_ptr` özel duruma başvuran bir nesne. Aksi halde, işlev null döndürür `exception_ptr` nesne.

### <a name="details"></a>Ayrıntılar

`current_exception` İşlevi yakalayan özel durum uçuştaki **catch** deyimi belirtir bir [özel durum bildirimi](../cpp/try-throw-and-catch-statements-cpp.md) deyimi.

Sonunda geçerli özel durumun yok Edicisi çağrılır **catch** özel durum oluşturmazsanız engelleyin. Ancak, çağırsanız bile `current_exception` işlevini yok edici içinde işlevi döndürür bir `exception_ptr` geçerli özel duruma başvuran bir nesne.

Art arda çağrılar `current_exception` işlev dönüş `exception_ptr` geçerli özel durumun farklı kopyalara başvuran nesneler. Sonuç olarak, kopyalar aynı ikili değerde olsalar da farklı kopyalara başvurduklarından, nesneler eşit olmayarak karşılaştırılır.

### <a name="seh-exceptions"></a>SEH özel durumları

Kullanırsanız **/eha** derleyici seçeneği, bir SEH özel durumu bir C++'ta catch **catch** blok. `current_exception` İşlevinin döndürdükleriyle bir `exception_ptr` SEH özel duruma başvuran bir nesne. Ve `rethrow_exception` işlevi, SEH özel durumu ile thetransported çağırırsanız oluşturur `exception_ptr` ve bağımsız değişkeni olarak.

`current_exception` İşlev null döndürür `exception_ptr` SEH çağırırsanız **__finally** sonlandırma işleyicisi bir **__except** özel durum işleyicisi veya **__except**filtre ifadesi.

Taşınan özel durumlar iç içe geçmiş özel durumları desteklemez. Bir iç içe geçmiş özel durum, bir özel durum işlenirken başka bir özel durumun oluşturulmasıyla ortaya çıkar. İç içe geçmiş özel durum yakalarsanız `EXCEPTION_RECORD.ExceptionRecord` veri üyesine işaret oluşan bir zincir `EXCEPTION_RECORD` ilişkili özel durumları açıklayan yapılar. `current_exception` İşlevi döndürdüğünden, iç içe geçmiş özel durumları desteklemez bir `exception_ptr` nesnesi `ExceptionRecord` veri üyesi sıfırlanmış.

Bir SEH özel durumu yakalarsanız, herhangi bir işaretçi tarafından başvurulan belleği yönetmeniz gerekir `EXCEPTION_RECORD.ExceptionInformation` veri üyesi dizisindeki. Bellek karşılık gelen ömrü boyunca geçerli olduğunu güvence altına almalıdır `exception_ptr` nesne ve bellek serbest bırakılır, `exception_ptr` nesnesi silindiğinde.

Yapılandırılmış özel durum (SE) çevirici işlevlerini özel durumları taşıma özelliğiyle birlikte kullanabilirsiniz. Bir SEH özel durumu bir C++ özel durumuna çevrilirse `current_exception` işlevinin döndürdükleriyle bir `exception_ptr` özgün SEH özel durumu yerine çevrilmiş özel duruma başvuran. `rethrow_exception` İşlevi ardından özgün özel çevrilmiş özel durumu oluşturur. SE Çevirici işlevleri hakkında daha fazla bilgi için bkz. [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).

## <a name="rethrowexception-function"></a>rethrow_exception İşlevi

Yakalanan bir özel durumu depolamanızın ardından bir `exception_ptr` nesnesi, birincil iş parçacığı nesneyi işleyebilir. Birincil iş parçacığı çağrı `rethrow_exception` ile birlikte çalışması `exception_ptr` ve bağımsız değişkeni olarak. `rethrow_exception` İşlevi, özel durumun ayıklar `exception_ptr` nesnesi ve ardından birincil iş parçacığının bağlamında özel durumu oluşturur. Varsa *p* parametresinin `rethrow_exception` işlevi, bir null `exception_ptr`, işlevin [gt; Std::bad_exception &](../standard-library/bad-exception-class.md).

Ayıklanan özel durum artık birincil iş parçacığında geçerli özel durumdur ve diğer özel durumlar gibi onu işleyebilirsiniz. Özel durumu yakalarsanız, onu hemen işleyebilir veya kullanan bir **throw** deyimi bir daha yüksek düzeydeki bir özel durum işleyicisine gönderebilirsiniz. Aksi halde, hiçbir şey yapmayın ve varsayılan sistem özel durum işleyicisinin işlemi sonlandırmasına izin verin.

## <a name="makeexceptionptr-function"></a>make_exception_ptr İşlevi

`make_exception_ptr` İşlevi, bağımsız değişken olarak bir sınıfın örneğini alır ve döndürür bir `exception_ptr` örneğe başvuran. Genellikle, belirttiğiniz bir [özel durum sınıfı](../standard-library/exception-class.md) bağımsız değişkeni olarak bir nesne `make_exception_ptr` herhangi bir sınıf nesnesi bağımsız değişken olsa da, işlev.

Çağırma `make_exception_ptr` işlevi içinde yakalama bir C++ özel durumu oluşturmaya eşdeğerdir bir **catch** blok ve ardından arama `current_exception` işlevini bir `exception_ptr` özel duruma başvuran bir nesne. Microsoft uyarlamasını `make_exception_ptr` işlevi oluşturmak ve ardından bir özel durum yakalamak daha verimlidir.

Bir uygulama genellikle gerektirmez `make_exception_ptr` işlevi ve kullanımı önerilmez.

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

**Başlık:** \<özel durum >

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)<br/>
[/EH (Özel Durum İşleme Modeli)](../build/reference/eh-exception-handling-model.md)<br/>
[/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)