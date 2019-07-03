---
title: Özel durumlar (C++/CX)
ms.date: 07/02/2019
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
ms.openlocfilehash: 93a3c096c79140787a46dcbd0ae6ec7edc0bf2e4
ms.sourcegitcommit: 9b904e490b1e262293a602bd1291a8f3045e755b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67552175"
---
# <a name="exceptions-ccx"></a>Özel durumlar (C++/CX)

Hata işleme C++/CX özel durumlarını temel alır. En temel düzeyde, Windows çalışma zamanı bileşenleri HRESULT değerleri olarak hataları bildirin. İçinde C++/CX, bu değerleri HRESULT değerini ve program aracılığıyla erişebileceğiniz bir dize açıklamasını içeren türü kesin belirlenmiş özel durumlar dönüştürülür.  Özel durumlar olarak gerçekleştirilen bir `ref class` türetilen `Platform::Exception`.  `Platform` Ad alanını tanımlayan farklı bir özel durum sınıfları en yaygın HRESULT değerleri için; aracılığıyla bildirilen diğer tüm değerler `Platform::COMException` sınıfı. Tüm özel durum sınıfları sahip bir [Exception::HResult](platform-exception-class.md#hresult) özgün HRESULT almak için kullanabileceğiniz bir alan. Ayrıca, kullanıcı kodu C++ dışında bir dilde yazılmış kod kaynağı olsa bile, özel durumun, özgün kaynak pinpoint yardımcı olmak üzere hata ayıklayıcı için çağrı yığını bilgileri inceleyebilirsiniz.

## <a name="exceptions"></a>Özel Durumlar

C++ programınızda, throw ve catch bir Windows çalışma zamanı işleminden gelen bir özel durum, türetilen bir özel durum `std::exception`, veya kullanıcı tanımlı bir tür. JavaScript'te kendi özel durumu yakalar kodu yazıldığında yalnızca, uygulama ikili arabiriminde (ABI) sınırı, örneğin, geçtiğinde bir Windows çalışma zamanı özel durum oluşturması gerekir. Bir olmayan - Windows çalışma zamanı zaman C++ özel durum ABI sınırına ulaştığında, özel durum çevrilir bir `Platform::FailureException` özel durum E_FAIL HRESULT temsil eder. ABI hakkında daha fazla bilgi için bkz: [C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

Bildirebilirsiniz bir [Platform::Exception](platform-exception-class.md) HRESULT parametresine veya bir HRESULT parametresine iki Oluşturucu birini kullanarak ve bir [Platform::String](platform-string-class.md)^ arasında geçirilen parametre ABI, işleme herhangi bir Windows çalışma zamanı uygulamaya. Ya da iki birini kullanarak bir özel durum bildirebilirsiniz [Exception::CreateException yöntemi](platform-exception-class.md#createexception) HRESULT parametresine veya bir HRESULT parametresi alan aşırı yüklemeler ve `Platform::String^` parametresi.

## <a name="standard-exceptions"></a>Standart özel durumlar

C++/CX tipik HRESULT hataları temsil eden standart özel durumlar, bir kümesini destekler. Her standart özel durum türetildiği [Platform::COMException](platform-comexception-class.md), hangi sırayla türetilir `Platform::Exception`. ABI sınırının ötesinde bir özel durum olduğunda, standart özel durumlardan birini throw gerekir.

Kendi özel durum türünden türetilemez `Platform::Exception`. Özel bir durum için oluşturmak için kullanıcı tanımlı bir HRESULT kullanan bir `COMException` nesne.

Aşağıdaki tablo standart özel durumlar listelenir.

|Ad|Temel alınan HRESULT|Açıklama|
|----------|------------------------|-----------------|
|COMException|*Kullanıcı tanımlı hresult*|Tanınmayan HRESULT bir COM yöntem çağrısından döndürülen zaman oluşturulur.|
|AccessDeniedException|E\_ERİŞİM ENGELLENDİ|Bir kaynağa veya özellik erişimi reddedilirse oluşturulur.|
|ChangedStateException|E\_DEĞİŞTİRİLEN\_DURUMU|Dolayısıyla yöntemin sonuçları geçersiz kılmalarını üst koleksiyon değiştikten sonra bir koleksiyon yineleyici veya koleksiyon görünümü yöntemler çağrıldığında oluşturulur.|
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|Bir COM sınıfı kaydedilmemiş olduğu zaman oluşturulur.|
|DisconnectedException|RPC\_E\_BAĞLANTI KESİLDİ|Bir nesnenin, istemcileriyle bağlantısı kesildiğinde oluşturulur.|
|FailureException|E\_BAŞARISIZ|Bir işlemi başarısız olduğunda oluşturulur.|
|InvalidArgumentException|E\_INVALIDARG|Bir yöntem için sağlanan bağımsız değişkenlerden biri geçerli olmadığında oluşturulur.|
|InvalidCastException|E\_NOINTERFACE|Bir tür başka bir türe dönüştüremezsiniz zaman oluşturulur.|
|NotImplementedException|E\_NOTIMPL|Bir arabirim yöntemi, bir sınıf üzerinde uygulanmadı durum.|
|NullReferenceException|E\_POINTER|Bir null Nesne başvurusu XML'deki başvuru girişimi olduğunda oluşturulur.|
|ObjectDisposedException|RO\_E\_KAPALI|Silinen bir nesne üzerinde bir işlem gerçekleştirildiğinde oluşturulur.|
|OperationCanceledException|E\_DURDUR|Bir işlem iptal edildiğinde oluşturulur.|
|OutOfBoundsException|E\_SINIRLARI|Bir işlem, geçerli aralığın dışında veri erişim girişiminde bulunduğunda oluşturulur.|
|OutOfMemoryException|E\_OUTOFMEMORY|İşlemi tamamlamak için bellek yetersiz olduğunda oluşturulur.|
|WrongThreadException|RPC\_E\_YANLIŞ\_İŞ PARÇACIĞI|Bir iş parçacığı için iş parçacığının grubunu ait olmayan bir proxy nesnesi için bir arabirim işaretçisi aracılığıyla çağırdığında oluşturulur.|

## <a name="hresult-and-message-properties"></a>HResult ve ileti özellikleri

Tüm özel durumlara sahip bir [HResult](platform-comexception-class.md#hresult) özelliği ve [ileti](platform-comexception-class.md#message) özelliği. [Exception::HResult](platform-exception-class.md#hresult) özelliği özel durumun sayısal HRESULT değerini temel alır. [Exception::Message](platform-exception-class.md#message) özelliği özel durumu açıklayan sistem tarafından sağlanan bir dize alır. Windows 8 ' deki iletiyi yalnızca hata ayıklayıcıda kullanılabilir ve salt okunur. Bu özel durumu yeniden olduğunda bunu değiştirilemez olduğunu anlamına gelir. Windows 8.1 ileti dizesi program yoluyla erişmeye ve özel durumu yeniden yeni bir ileti sağlayın. Çağrı yığını bilgi de zaman uyumsuz yöntem çağrıları için çağrı yığınını da dahil olmak üzere hata ayıklayıcı, kullanıma sunulmuştur.

### <a name="examples"></a>Örnekler

Bu örnek, zaman uyumlu işlemler için bir Windows çalışma zamanı özel durum gösterilmektedir:

[!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]

Sonraki örnek, özel durum yakalamak gösterilmektedir.

[!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]

Zaman uyumsuz bir işlemi sırasında oluşturulan özel durumları yakalamak için görev sınıfı kullanın ve bir hata işleme devamlılık ekleyin. Hata işleme devamlılık, kodunuzdaki tüm olası özel durumları tek bir noktada işleyebilmeniz geri çağırma iş parçacığı için diğer iş parçacıkları üzerinde oluşturulan özel durumları sürekliliğe devreder. Daha fazla bilgi için [C++ zaman uyumsuz programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps).

## <a name="unhandlederrordetected-event"></a>UnhandledErrorDetected olay

Windows 8.1 abone olabileceğiniz [Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected](/uwp/api/windows.applicationmodel.core.icoreapplicationunhandlederror.unhandlederrordetected) hakkında işleminin çökmesine işlenmemiş hataları erişim sağlayan statik olay. Hata nereden geldiğini bağımsız olarak, bu işleyici olarak ulaştığında bir [Windows::ApplicationModel::Core::UnhandledError](/uwp/api/windows.applicationmodel.core.unhandlederror) oturum event args geçirilen nesne. Çağırdığınızda `Propagate` nesnesinde oluşturur ve oluşturur bir `Platform::*Exception` hata koduna karşılık gelen türü. Catch bloğu içinde kullanıcı durumunu gerekirse kaydedebilir ve sonra ya da çağırarak ciddiyeti işlemin sonlandırılmasına izin `throw`, veya program bilinen bir duruma geri dönmek için bir şey. Aşağıdaki örnek, temel düzeni gösterir:

App.xaml.h içinde:

```cpp
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);
```

App.xaml.cpp içinde:

```cpp
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

C++/CX kullanmayan `finally` yan tümcesi.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dil Başvurusu](visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](namespaces-reference-c-cx.md)
