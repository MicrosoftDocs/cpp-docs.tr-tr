---
title: "Özel durumlar (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
caps.latest.revision: "22"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: b9b7a5af4816ff638918ccf7478465fe120e8e67
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="exceptions-ccx"></a>Özel durumlar (C + +/ CX)

Hata işleme C + +/ CX özel durumlarını temel alır. En temel düzeyde Windows çalışma zamanı bileşenleri hataları HRESULT değeri olarak rapor. C + +/ CX, bu değerler HRESULT değeri ve program aracılığıyla erişebilirsiniz dize açıklamasını içeren kesin türü belirtilmiş özel durumlar dönüştürülür.  Özel durumlar olarak gerçekleştirilen bir `ref class` , türetilen `Platform::Exception`.  `Platform` Ad alanını tanımlayan ayrı özel durum sınıfları en yaygın HRESULT değerleri için; diğer tüm değerler aracılığıyla bildirilir `Platform::COMException` sınıfı. Tüm özel durum sınıfları sahip bir [Exception::HResult](platform-exception-class.md#hresult) özgün HRESULT almak için kullanabileceğiniz alan. Ayrıca, kullanıcı kodu C++ dışındaki bir dilde yazıldı kodda kaynaklanan olsa bile, özel durumun, özgün kaynak belirlemenize yardımcı olabilecek hata ayıklayıcısında için çağrı yığını bilgileri inceleyebilirsiniz.  
  
## <a name="exceptions"></a>Özel Durumlar  
 C++ programınız throw ve catch Windows çalışma zamanı işleminden gelen bir özel durum, türetilmiş bir özel durum `std::exception`, veya kullanıcı tanımlı tür. JavaScript'te, özel durum yakalar kod yazıldığında yalnızca, uygulama ikili arabirimi (ABI) sınır Örneğin, geçtiğinde Windows çalışma zamanı özel durum vardır. Windows çalışma zamanı C++ özel durum ABI sınırına ulaştığında, özel durum veri dönüştürülür bir `Platform::FailureException` özel durum E_FAIL HRESULT temsil eder. ABI hakkında daha fazla bilgi için bkz: [C++'da Windows çalışma zamanı bileşenleri oluşturma](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md).  
  
 Bildirebilirsiniz bir [Platform::Exception](platform-exception-class.md) HRESULT parametresini ya da bir HRESULT parametresi ele iki oluşturucular birini kullanarak ve [Platform::String](platform-string-class.md)^ arasında geçirilen parametre ABI, işleme tüm Windows mağazası uygulaması. Veya iki birini kullanarak bir özel durum bildirebilirsiniz [Exception::CreateException yöntemi](platform-exception-class.md#createexception) HRESULT parametresini ya da bir HRESULT parametre almayan aşırı ve `Platform::String^` parametresi.  
  
## <a name="standard-exceptions"></a>Standart özel durumlar  
 C + +/ CX tipik HRESULT hataları temsil eden standart özel durumlar bir kümesini destekler. Her standart özel durum türetilen [Platform::COMException](platform-comexception-class.md), hangi sırayla türetilen `Platform::Exception`. ABI sınırından bir özel durum, standart özel durumlardan birini throw gerekir.  

 Kendi özel durum türünden türetilemez `Platform::Exception`. Özel bir özel durum için oluşturmak için bir kullanıcı tarafından tanımlanan HRESULT kullanın bir `COMException` nesnesi.  
  
 Aşağıdaki tabloda standart özel durumlar listelenir.  
  
|Ad|Temel alınan HRESULT|Açıklama|  
|----------|------------------------|-----------------|  
|COMException|*Kullanıcı tanımlı hresult*|Tanınmayan HRESULT bir COM yöntemi çağrısından döndürülen zaman oluşturulur.|  
|AccessDeniedException|E_ACCESSDENIED|Bir kaynak veya özellik için erişim reddedildi zaman oluşturulur.|  
|ChangedStateException|E_CHANGED_STATE|Böylece yöntemi sonuçlarını geçersiz kılmalarını üst koleksiyon değiştikten sonra bir koleksiyon yineleyici ya da bir koleksiyon görünümü yöntemler çağrıldığında oluşturulur.|  
|ClassNotRegisteredException|REGDB_E_CLASSNOTREG|Bir COM sınıfı kaydedilmemiş zaman oluşturulur.|  
|DisconnectedException|RPC_E_DISCONNECTED|Bir nesne istemcilerinden zaman oluşturulur.|  
|FailureException|E_FAIL|Bir işlem başarısız olduğunda oluşturulur.|  
|InvalidArgumentException|E_INVALIDARG|Bir yöntem için sağlanan bağımsız değişkenlerden biri geçerli değilse oluşturulur.|  
|InvalidCastException|E_NOINTERFACE|Bir başka bir türüne atanamaz zaman oluşturulur.|  
|NotImplementedException|E_NOTIMPL|Arabirim yöntemi bir sınıf üzerinde uygulanmadı dönerse oluşturulur.|  
|NullReferenceException|E_POINTER|XML'deki bir null Nesne başvuru kaynağı girişimi olduğunda oluşturulur.|  
|ObjectDisposedException|RO_E_CLOSED|Silinen bir nesne üzerinde bir işlemi gerçekleştirildiğinde oluşturulur.|  
|OperationCanceledException|E_ABORT|Bir işlem iptal edildiğinde oluşturulur.|  
|OutOfBoundsException|E_BOUNDS|Bir işlem, geçerli aralığın dışında veri erişim girişiminde bulunduğunda oluşur.|  
|OutOfMemoryException|E_OUTOFMEMORY|İşlemi tamamlamak için bellek yetersiz olduğunda oluşturulur.|  
|WrongThreadException|RPC_E_WRONG_THREAD|Bir iş parçacığı için iş parçacığının grubunu ait olmayan bir proxy nesnesi için bir arabirim işaretçisi aracılığıyla çağırdığında oluşturulur.|  
  
## <a name="hresult-and-message-properties"></a>HResult ve ileti özellikleri  
 Tüm özel durumlara sahip bir [HResult](platform-comexception-class.md#hresult) özelliği ve [ileti](platform-comexception-class.md#message) özelliği. [Exception::HResult](platform-exception-class.md#hresult) özelliği, özel durumun sayısal HRESULT değeri temel alır. [Exception::Message](platform-exception-class.md#message) özelliği özel durumu açıklayan sistem tarafından sağlanmış bir dize alır. Windows 8 ' deki ileti yalnızca hata ayıklayıcıda kullanılabilir ve salt okunur durumdadır. Bu özel durumun yeniden oluşturulması zaman değiştiremezsiniz olduğunu anlamına gelir. Windows 8.1 içinde ileti dizesi programlı olarak erişmek ve özel durumun yeniden oluşturulması gerekirse, yeni bir ileti sağlayın. Daha iyi çağrı yığını bilgileri ayıklayıcısında callstacks zaman uyumsuz yöntem çağrıları için de dahil olmak üzere de kullanılabilir.  
  
### <a name="examples"></a>Örnekler  
 Bu örnekte, zaman uyumlu işlemler için Windows çalışma zamanı özel throw gösterilmektedir:  
  
 [!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]  
  
 Sonraki örnek catch özel durum gösterilmiştir.  
  
 [!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]  
  
 Zaman uyumsuz bir işlem sırasında oluşturulan özel durumları yakalamak için görev sınıfı ve ekleyin bir hata işleme devamlılık. Hata işleme devamlılık geri çağıran iş parçacığı için başka bir iş parçacığı üzerinde oluşturulur ve böylece tüm olası özel durumlar, yalnızca tek bir noktada kodunuzda işleyebilir özel durumlar sıralar. Daha fazla bilgi için bkz: [C++ zaman uyumsuz programlama](http://msdn.microsoft.com/library/windows/apps/Hh780559.aspx).  
  
## <a name="unhandlederrordetected-event"></a>UnhandledErrorDetected olayı  
 Windows 8.1 için abone olabilirsiniz [Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected](http://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.core.coreapplication.unhandlederrordetected.aspx) hakkında işleminin çökmesine işlenmemiş hatalarını erişim sağlayan statik olay. Hata geldiği bağımsız olarak, bu işleyici olarak ulaştığında bir [Windows::ApplicationModel::Core::UnhandledError](http://msdnstage.redmond.corp.microsoft.com/library/windows/apps/windows.applicationmodel.core.unhandlederror.aspx) oturum olay bağımsız değişken geçirildi nesnesi. Çağırdığınızda `Propagate` nesnesindeki oluşturur ve oluşturur bir `Platform::*Exception` hata koduna karşılık gelen türü. Catch blokları, kullanıcı durumu gerekirse kaydedebilir ve ya da çağırarak ciddiyeti işlemin izin `throw`, veya program bilinen bir duruma geri almak için bir şeyler. Aşağıdaki örnek, temel düzeni gösterir:  
  
```  
  
// In app.xaml.h:  
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);  
  
// In app.xaml.cpp  
  
// Subscribe to the event, for example in the app class constructor:  
Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected += ref new EventHandler<UnhandledErrorDetectedEventArgs^>(this, &App::OnUnhandledException);  
  
// Event handler implementation:  
void App::OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e)  
{  
    auto err = e->UnhandledError;  
  
    if (!err->Handled) //Propagate has not been called on it yet.  
{  
     try  
    {  
        err->Propagate();  
    }  
    // Catch any specific exception types if you know how to handle them  
    catch (AccessDeniedException^ ex)  
    {  
        // TODO: Log error and either take action to recover  
        // or else re-throw exception to continue fail-fast  
    }  
  
}  
  
```  
  
### <a name="remarks"></a>Açıklamalar  
 C + +/ CX kullanmaz `finally` yan tümcesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Dil Başvurusu](visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](namespaces-reference-c-cx.md)