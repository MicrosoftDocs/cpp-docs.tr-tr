---
title: "Özel durumları iş parçacıkları arasında taşıma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
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
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1ccbda062d28cdbdaafcbae68793b6583f31a3be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="transporting-exceptions-between-threads"></a>Özel Durumları İş Parçacıkları Arasında Taşıma
Visual C++ destekler *bir özel durum taşıma* için başka bir iş parçacığından diğerine. Taşınan özel durumlar bir iş parçacığındaki özel durumu yakalamanızı sağlar ve sonra özel durumun farklı bir iş parçacığında oluşmuş gibi görünmesini sağlar. Örneğin, bu özelliği birincil iş parçacığının ikincil iş parçacıkları tarafından oluşturulan tüm özel durumları işlediği çok iş parçacıklı bir uygulamayı yazmak için kullanabilirsiniz. Özel durum taşımaları, çoğunlukla paralel programlama kitaplıkları veya sistemleri oluşturan geliştiriciler için yararlıdır. Taşınmasını özel durumlar uygulamak için Visual C++ sağlar [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) türü ve [current_exception](../standard-library/exception-functions.md#current_exception), [rethrow_exception](../standard-library/exception-functions.md#rethrow_exception), ve [make_ exception_ptr](../standard-library/exception-functions.md#make_exception_ptr) işlevleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
namespace std   
{  
   typedef unspecified exception_ptr;   
   exception_ptr current_exception();  
   void rethrow_exception(exception_ptr p);  
   template<class E>   
       exception_ptr make_exception_ptr(E e) noexcept;  
}  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`unspecified`|Uygulamak için kullanılan belirtilmeyen bir iç sınıf `exception_ptr` türü.|  
|`p`|Bir `exception_ptr` başvuruda bulunan bir özel durum nesnesi.|  
|`E`|Bir özel durumu temsil eden sınıf.|  
|`e`|Parametre örneği `E` sınıfı.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 `current_exception` İşlev döndürür bir `exception_ptr` şu anda devam ediyor özel durum başvuran nesne. Hiçbir özel durum ediyor olup olmadığını döndürür işlevi bir `exception_ptr` herhangi bir özel durum ile ilişkili değil nesnesi.  
  
 `make_exception_ptr` İşlev döndürür bir `exception_ptr` tarafından belirtilen özel durum başvuran nesne `e` parametresi.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="scenario"></a>Senaryo  
 Bir değişkenin çalışma miktarını işleyebilmek için ölçeklenebilen bir uygulama oluşturmak istediğinizi düşünün. Bunu gerçekleştirmek için çok iş parçacıklı bir uygulama tasarlayın; bu uygulamada ilk, birincil iş parçacığı işi yapmak için gereken sayıda ikincil iş parçacığını oluşturur. İkincil iş parçacıkları yükleri dengelemek, verimi artırmak ve kaynakları yönetmek için birincil iş parçacıklarına yardımcı olur. İşi dağıtarak, çok iş parçacıklı uygulamalar tek iş parçacıklı uygulamalardan daha iyi performans gösterir.  
  
 Ancak, ikincil bir iş parçacığı bir özel durum oluşturursa, birincil iş parçacığının bu durumu işlemesini istersiniz. Bunun nedeni, ikincil iş parçacığı sayısı ne olursa olsun uygulamanızın tutarlı ve birleştirilmiş bir şekilde özel durumları işlemesini istemenizdir.  
  
## <a name="solution"></a>Çözüm  
 C++ Standard, önceki senaryonun işlenmesi için, bir özel durumun iş parçacıkları arasında taşınmasını destekler. İkincil bir iş parçacığı bir özel durum oluşturursa, bu özel durum hale *geçerli özel durumun*. Gerçek dünya benzerliği tarafından geçerli özel durumun olarak kabul edilir *yürütülen*. Geçerli özel durum, özel durum işleyicisi tarafından dönüşü yakalanana kadar uçuştadır.  
  
 İkincil iş parçacığı içinde geçerli özel durumun yakalayabilir bir `catch` engelleme ve ardından arama `current_exception` işlev özel durum depolamak için bir `exception_ptr` nesnesi. `exception_ptr` Nesne İkincil iş parçacığı ve birincil iş parçacığı için kullanılabilir olmalıdır. Örneğin, `exception_ptr` Nesne erişimini mutex tarafından denetlenen bir genel değişkeni olabilir. Terim *bir özel durum taşıma* bir iş parçacığında özel durum, başka bir iş parçacığı tarafından erişilebilen bir forma dönüştürülebilir anlamına gelir.  
  
 Ardından, birincil iş parçacığı çağırır `rethrow_exception` ayıklar ve özel durumu oluşturur işlevin `exception_ptr` nesnesi. Özel durum oluştuğunda, birincil iş parçacığındaki geçerli özel durum haline gelir. Diğer bir deyişle, özel durum birincil iş parçacığında oluşmuş görünür.  
  
 Son olarak, birincil iş parçacığı içinde geçerli özel durumun yakalayabilir bir `catch` engelleme işlemesi veya daha yüksek bir düzeyinde özel durum işleyici atar. Ya da birincil iş parçacığı özel durumu yoksayar ve işlemi sonlandırmaya izin verir.  
  
 Çoğu uygulamada özel durumların iş parçacıkları arasında taşınması gerekmez. Ancak, sistem işi ikincil iş parçacıkları, işlemci veya çekirdek arasında bölebildiğinden, bu özellik paralel bir bilgi işlem sisteminde yararlıdır. Paralel bir bilgi işlem ortamında, tek ve özel bir iş parçacığı ikincil iş parçacıklarından gelen tüm özel durumları işleyebilir ve herhangi bir uygulama için tutarlı bir özel durum işleme modeli sunabilir.  
  
 C++ Standartları komitesi teklifi hakkında daha fazla bilgi için, internette "Özel Durumları İş Parçacıkları Arasında Taşıma için Dil Desteği" başlıklı N2179 belge numarasını arayın.  
  
## <a name="exception-handling-models-and-compiler-options"></a>Özel Durum-İşleme Modelleri ve Derleyici Seçenekleri  
 Uygulamanızın özel durum işleme modeli, bir özel durumu yakalayıp taşıyabileceğini ya da bunu yapamayacağınızı belirler. Visual C+; C++ özel durumlarını, yapılandırılmış özel durum işleme (SEH) özel durumlarını ve ortak dil çalışma zamanı (CLR) özel durumlarını işleyebilen üç modeli destekler. Kullanım [/EH](../build/reference/eh-exception-handling-model.md) ve [/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçenekleri, uygulamanızın özel durum işleme modeli belirtin.  
  
 Yalnızca aşağıdaki derleyici seçeneklerinin ve programlama deyimlerinin birleşimi bir özel durumu taşıyabilir. Diğer birleşimler özel durumları yakalayamaz ya da özel durumları yakalasa da taşıyamaz.  
  
-   **/EHa** derleyici seçeneği ve `catch` deyimi SEH ve C++ özel durum taşıma.  
  
-   **/EHa**, **/EHs**, ve **/EHsc** derleyici seçenekleri ve `catch` deyimi C++ özel durumlarını taşıma.  
  
-   **/CLR** veya **/CLR: pure** derleyici seçeneği ve `catch` deyimi C++ özel durumlarını taşıma. **/CLR** derleyici seçenekleri kapsıyor belirtimi **/EHa** seçeneği. Derleyicinin yönetilen özel durumların taşınmasını desteklemediğini unutmayın. Yönetilen türetilmiş özel durumları çünkü [System.Exception sınıfı](../standard-library/exception-class.md), zaten ortak languange çalışma zamanı tesis kullanarak iş parçacıkları arasında taşıma nesnelerdir.  
  
    > [!IMPORTANT]
    >  Belirttiğiniz öneririz **/EHsc** derleyici seçeneği ve catch yalnızca C++ özel durum. Kullanırsanız, kendiniz için bir güvenlik tehdidi ortaya **/EHa** veya **/CLR** derleyici seçeneği ve **catch** deyim üç nokta ile  *özel durum bildirimi* (`catch(...)`). Büyük olasılıkla kullanmayı düşündüğünüz `catch` birkaç belirli özel durumları yakalamak için deyimi. Ancak, `catch(...)` deyimi önemli olmalıdır beklenmeyen olanlar da dahil olmak üzere tüm C++ ve SEH özel durumları yakalar. Beklenmeyen bir özel durumu yoksayarsanız ya da düzgün işleyemezseniz, kötü amaçlı yazılımlar programınızın güvenliğine zarar vermek için bu fırsatı kullanabilir.  
  
## <a name="usage"></a>Kullanım  
 Aşağıdaki bölümlerde kullanarak özel durumlar aktarım nasıl `exception_ptr` türü ve `current_exception`, `rethrow_exception`, ve `make_exception_ptr` işlevleri.  
  
### <a name="exceptionptr-type"></a>exception_ptr Türü  
 Kullanım bir `exception_ptr` geçerli özel durumun veya bir kullanıcı tarafından belirtilen özel örneği başvurmak için nesne. Microsoft uygulama, bir özel durum tarafından temsil edilen bir [EXCEPTION_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082) yapısı. Her `exception_ptr` nesne içeren bir kopyasına işaret eden bir özel durum başvuru alanı `EXCEPTION_RECORD` yapısı özel durumu temsil eder.  
  
 Ne zaman bildirdiğiniz bir `exception_ptr` değişkeni, değişken herhangi bir özel durum ile ilişkili değil. Diğer bir deyişle, özel durum başvuru alanı NULL olur. Bu tür bir `exception_ptr` nesne adlı bir *null exception_ptr*.  
  
 Kullanım `current_exception` veya `make_exception_ptr` işlevi bir özel durum olarak atamak için bir `exception_ptr` nesnesi. Bir özel durum atadığınızda bir `exception_ptr` değişken, değişkenin özel durum başvurusu alan özel bir kopyasını gösterir. Özel durum kopyalamak için yeterli bellek varsa, özel durum başvurusu alan bir kopyasına işaret eden bir [std::bad_alloc](../standard-library/bad-alloc-class.md) özel durum. Varsa `current_exception` veya `make_exception_ptr` işlevi başka bir nedenle, işlev çağrıları özel kopyalayamıyor [sonlandırmak](../c-runtime-library/reference/terminate-crt.md) işlevi geçerli işleminden çıkış yapar.  
  
 Adını rağmen bir `exception_ptr` nesne kendisi gösteren bir işaretçidir. İşaretçi semantiği uyma değil ve işaretçi üye erişimle kullanılamaz (`->`) veya (*) yöneltme işleçleri. `exception_ptr` Nesneyi, hiçbir ortak veri üyeleri veya üye işlevleri sahiptir.  
  
 **Karşılaştırmaları:**  
  
 Eşittir kullanabilirsiniz (`==`) ve eşit değil (`!=`) iki Karşılaştırılacak işleçleri `exception_ptr` nesneleri. İşleçler ikili değeri (bit desenini) ile karşılaştırın değil `EXCEPTION_RECORD` özel durumları temsil eden yapılar. Bunun yerine, özel durum başvurusu alanına adresleri işleçleri karşılaştırmak `exception_ptr` nesneleri. Sonuç olarak, bir null `exception_ptr` ve eşit olarak karşılaştırmak NULL değer.  
  
### <a name="currentexception-function"></a>current_exception İşlevi  
 Çağrı `current_exception` işlevi bir `catch` bloğu. Bir özel durum uçuş modunda ise ve `catch` bloğu özel durum yakalayabilir `current_exception` işlev döndürür bir `exception_ptr` başvuruda bulunan özel durum nesnesi. Aksi takdirde işlevi null değeri döndürür `exception_ptr` nesnesi.  
  
 **Ayrıntılar:**  
  
 `current_exception` İşlevi yakalar mı bağımsız olarak yürütülen özel durum `catch` deyimi belirten bir [özel durum bildirimi](../cpp/try-throw-and-catch-statements-cpp.md) deyimi.  
  
 Geçerli özel durumun yıkıcı sonunda çağrılır `catch` , özel durumun yeniden oluşturulması değil, engelleyin. Ancak, bile çağırırsanız `current_exception` işlev yıkıcı işlevi döndürür bir `exception_ptr` geçerli özel durumun başvuran nesne.  
  
 Art arda çağrılar `current_exception` işlev dönüş `exception_ptr` geçerli özel durumun farklı kopyalarını başvuran nesneleri. Sonuç olarak, kopyalar aynı ikili değerde olsalar da farklı kopyalara başvurduklarından, nesneler eşit olmayarak karşılaştırılır.  
  
 **SEH özel durumlar:**  
  
 Kullanırsanız **/EHa** derleyici seçeneği, bir C++ SEH istisna yakalayabilir `catch` bloğu. `current_exception` İşlev döndürür bir `exception_ptr` SEH özel durumu başvuran nesne. Ve `rethrow_exception` işlevi ile thetransported çağırırsanız SEH özel durum oluşturur `exception_ptr` nesnesi bağımsız değişkeni olarak.  
  
 `current_exception` İşlevi null değeri döndürür `exception_ptr` bir SEH çağırırsanız `__finally` sonlandırma işleyicisi bir `__except` özel durum işleyici veya `__except` filtre ifadesi.  
  
 Taşınan özel durumlar iç içe geçmiş özel durumları desteklemez. Bir iç içe geçmiş özel durum, bir özel durum işlenirken başka bir özel durumun oluşturulmasıyla ortaya çıkar. İç içe geçmiş bir özel durum catch `EXCEPTION_RECORD.ExceptionRecord` veri üyesi için bir zinciri işaret `EXCEPTION_RECORD` ilişkili özel durumları açıklayın yapıları. `current_exception` İşlevi döndürdüğü olduğundan iç içe geçmiş özel durumlar desteklemiyor bir `exception_ptr` nesnesindeki `ExceptionRecord` veri üyesi Sıfırlı çıkışı.  
  
 SEH özel durumu yakalayın, tüm işaretçi tarafından başvurulan bellek yönetmelisiniz `EXCEPTION_RECORD.ExceptionInformation` veri üyesi dizisi. Bellek ilgili ömrü boyunca geçerli olduğunu güvence altına almalıdır `exception_ptr` nesne ve belleği serbest bırakılır zaman `exception_ptr` nesne silinir.  
  
 Yapılandırılmış özel durum (SE) çevirici işlevlerini özel durumları taşıma özelliğiyle birlikte kullanabilirsiniz. C++ özel durum için SEH istisna çevrilmiş `current_exception` işlev döndürür bir `exception_ptr` orijinal SEH özel durumu yerine çevrilmiş özel durum başvuruyor. `rethrow_exception` İşlevi sonradan değil orijinal özel durumu çevrilmiş özel durum oluşturur. SE Çeviricisi işlevleri hakkında daha fazla bilgi için bkz: [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).  
  
### <a name="rethrowexception-function"></a>rethrow_exception İşlevi  
 Yakalanan bir özel durum depolamak sonra bir `exception_ptr` nesnesi, birincil iş parçacığı nesne işleyebilir. Birincil iş parçacığı arama `rethrow_exception` ile birlikte çalışması `exception_ptr` nesnesi bağımsız değişkeni olarak. `rethrow_exception` İşlevi ayıklar özel durumundan `exception_ptr` nesne ve ardından birincil iş parçacığının bağlamında özel durum oluşturur. Varsa `p` parametresinin `rethrow_exception` işlevi, bir null `exception_ptr`, işlev oluşturur [std::bad_exception](../standard-library/bad-exception-class.md).  
  
 Ayıklanan özel durum artık birincil iş parçacığında geçerli özel durumdur ve diğer özel durumlar gibi onu işleyebilirsiniz. Özel durum catch, hemen işlemek veya kullanmak bir `throw` daha yüksek bir düzeyinde özel durum işleyici göndermek için deyimi. Aksi halde, hiçbir şey yapmayın ve varsayılan sistem özel durum işleyicisinin işlemi sonlandırmasına izin verin.  
  
### <a name="makeexceptionptr-function"></a>make_exception_ptr İşlevi  
 `make_exception_ptr` İşlev bağımsız değişkeni olarak bir sınıfın örneğini alır ve ardından döndürür bir `exception_ptr` örneği başvuruyor. Genellikle, belirttiğiniz bir [özel durum sınıfı](../standard-library/exception-class.md) bağımsız değişkeni olarak nesne `make_exception_ptr` herhangi bir sınıf nesnesi bağımsız değişkeni olsa da, işlev.  
  
 Çağırma `make_exception_ptr` işlevi içinde yakalama C++ özel durum atma için eşdeğer bir `catch` bloğu ve ardından çağırma `current_exception` döndürülecek işlevi bir `exception_ptr` başvuruda bulunan özel durum nesnesi. Microsoft uyarlamasını `make_exception_ptr` işlevidir atma ve bir özel durum yakalama daha verimlidir.  
  
 Bir uygulama tarafından genellikle gerektirmez `make_exception_ptr` işlevi ve biz kullanımı önerilmemektedir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, standart C++ özel durumunu ve özel bir C++ özel durumunu bir iş parçacığından diğerine taşır.  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durum işleme](../cpp/exception-handling-in-visual-cpp.md)     
 [/EH (özel durum işleme modeli)](../build/reference/eh-exception-handling-model.md)   
 [/ CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)