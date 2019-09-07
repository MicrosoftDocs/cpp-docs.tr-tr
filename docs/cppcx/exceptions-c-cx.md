---
title: Özel durumlarC++(/CX)
ms.date: 07/02/2019
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
ms.openlocfilehash: ade406dc5db6022978f83715555c425caef4375b
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740170"
---
# <a name="exceptions-ccx"></a>Özel durumlarC++(/CX)

/CX 'de C++hata işleme özel durumları temel alır. En temel düzeyde, Windows Çalışma Zamanı bileşenleri hataları HRESULT değeri olarak bildirir. /CX C++içinde bu değerler, bir HRESULT değeri ve programlı olarak erişebileceğiniz bir dize açıklaması içeren, kesin tür belirtilmiş özel durumlara dönüştürülür.  Özel durumlar, öğesinden `ref class` `Platform::Exception`türetilen olarak uygulanır.  Ad alanı, en yaygın HRESULT değerleri için farklı özel durum sınıflarını tanımlar; diğer tüm değerler `Platform::COMException` sınıfı aracılığıyla raporlanır. `Platform` Tüm özel durum sınıflarının, özgün HRESULT 'yi almak için kullanabileceğiniz bir [özel durum:: HRESULT](platform-exception-class.md#hresult) alanı vardır. Ayrıca, hata ayıklayıcıda Kullanıcı kodu için çağrı yığını bilgilerini, dışında bir dilde yazılmış koddan kaynaklansa bile, özel durumun özgün kaynağını belirlemenize yardımcı olabilecek şekilde inceleyebilirsiniz C++.

## <a name="exceptions"></a>Özel Durumlar

C++ Programınızda, bir Windows çalışma zamanı işleminden gelen bir özel durumu, öğesinden `std::exception`türetilmiş bir özel durumu veya Kullanıcı tanımlı bir türü oluşturabilir ve yakalayabilirsiniz. Yalnızca bir Windows Çalışma Zamanı özel durum oluşturmanız gerekir, örneğin özel durumunuzu yakalayan kodun JavaScript 'te yazıldığı durumlar gibi,. Windows çalışma zamanı C++ olmayan bir özel durum ABI sınırına ulaştığında, özel durum, E_FAIL hresult temsil eden bir `Platform::FailureException` özel duruma çevrilir. ABı hakkında daha fazla bilgi için bkz. [içinde C++Windows çalışma zamanı bileşenleri oluşturma ](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

Bir HRESULT parametresi veya bir HRESULT parametresi alan iki oluşturucudan birini kullanarak bir [Platform:: Exception](platform-exception-class.md) , ABI üzerinden onu işleyen herhangi bir Windows çalışma zamanı uygulamasına geçirilebilen bir [Platform:: String](platform-string-class.md)^ parametresi de bildirebilirsiniz. Ya da iki özel durumdan birini kullanarak bir özel durum bildirebilirsiniz [::](platform-exception-class.md#createexception) bir HRESULT parametresi veya bir HRESULT parametresi veya bir HRESULT parametresi `Platform::String^` ya da bir parametre alan CreateException yöntemi aşırı yüklemeleri.

## <a name="standard-exceptions"></a>Standart özel durumlar

C++/CX tipik HRESULT hatalarını temsil eden bir dizi standart özel durumu destekler. Her bir standart özel durum [Platform:: COMException](platform-comexception-class.md)sınıfından türetilir ve bu, sırasıyla `Platform::Exception`türetilir. ABı sınırında bir özel durum oluşturduğunuzda, standart özel durumlardan birini oluşturmanız gerekir.

Kendi özel durum türünden `Platform::Exception`bir türetebilirsiniz. Özel bir özel durum oluşturmak için Kullanıcı tanımlı HRESULT kullanarak bir `COMException` nesne oluşturun.

Aşağıdaki tabloda standart özel durumlar listelenmektedir.

|Ad|Temel alınan HRESULT|Açıklama|
|----------|------------------------|-----------------|
|COMException|*Kullanıcı tanımlı HRESULT*|Bir COM yöntem çağrısından tanınmayan HRESULT döndürüldüğünde oluşturulur.|
|AccessDeniedException Oluşturucusu|E\_ACCESSREDDEDİLDİ|Bir kaynak veya özelliğe erişim reddedildiğinde oluşturulur.|
|Changedstateexception Oluşturucusu|E\_DEĞİŞTİ\_DURUMU|Üst koleksiyon değiştirildikten sonra bir koleksiyon yineleyicisinin veya koleksiyon görünümünün yöntemleri çağrıldığında, bu nedenle yöntemin sonuçları geçersiz kılınırken oluşturulur.|
|Classnotregisteredexception Oluşturucusu|REGDB\_E\_CLASSNOTREG|Bir COM sınıfı kaydedilmemişse oluşturulur.|
|Disconnectedexception Oluşturucusu|RPC\_E\_BAĞLANTISI KESİLDİ|Bir nesnenin istemcileriyle bağlantısı kesildiğinde oluşturulur.|
|FailureException Oluşturucusu|E\_BAŞARISIZ|Bir işlem başarısız olduğunda oluşturulur.|
|InvalidArgumentException Oluşturucusu|E\_İNVALİDARG|Bir yönteme verilen bağımsız değişkenlerden biri geçerli değilse oluşturulur.|
|InvalidCastException|E\_NOINTERFACE|Bir tür başka bir türe yayınlanatılamayacağını ortaya atılır.|
|NotImplementedException|E\_NOTİMPL|Bir arabirim yöntemi bir sınıfa uygulanmadıysa oluşturulur.|
|Durumu|E\_İŞARETÇİSİ|Bir null nesne başvurusunu serbest bırakma girişimi olduğunda oluşturulur.|
|ObjectDisposedException|\_E\_KAPALI RO|Atılmış bir nesne üzerinde bir işlem gerçekleştirildiğinde oluşturulur.|
|OperationCanceledException|E\_-DURDUR|Bir işlem iptal edildiğinde oluşturulur.|
|Outofboundsexception Oluşturucusu|E\_SINIRLARI|Bir işlem geçerli Aralık dışında veriye erişmeye çalıştığında oluşturulur.|
|OutOfMemoryException|E\_OUTOFMEMORY|İşlemi gerçekleştirmek için yeterli bellek kalmadığında oluşturulur.|
|Wrongthreadexception Oluşturucusu|RPC\_E\_YANLIŞ\_İŞ PARÇACIĞI|Bir iş parçacığı, iş parçacığının grubuna ait olmayan bir ara sunucu nesnesi için olan bir arabirim işaretçisi aracılığıyla çağırdığında oluşturulur.|

## <a name="hresult-and-message-properties"></a>HResult ve Ileti özellikleri

Tüm özel durumların bir [HRESULT](platform-comexception-class.md#hresult) özelliği ve bir [ileti](platform-comexception-class.md#message) özelliği vardır. [Özel durum:: HRESULT](platform-exception-class.md#hresult) özelliği, özel durumun temel ALıNAN sayısal HRESULT değerini alır. [Exception:: Message](platform-exception-class.md#message) özelliği, özel durumu tanımlayan sistem tarafından sağlanan dizeyi alır. Windows 8 ' de ileti yalnızca hata ayıklayıcıda kullanılabilir ve salt okunurdur. Bu, özel durumu yeniden oluştururken değiştiremeyeceğiniz anlamına gelir. Windows 8.1 ' de, ileti dizesine programlı bir şekilde erişebilir ve özel durumu yeniden oluşturursanız yeni bir ileti sağlayabilirsiniz. Zaman uyumsuz yöntem çağrıları için çağrı yığınları dahil olmak üzere, hata ayıklayıcıda daha iyi çağrı yığını bilgileri de mevcuttur.

### <a name="examples"></a>Örnekler

Bu örnek, zaman uyumlu işlemler için Windows Çalışma Zamanı özel durumunun nasıl oluşturulacağını gösterir:

[!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]

Sonraki örnekte özel durumun nasıl yakalandığınız gösterilmektedir.

[!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]

Zaman uyumsuz bir işlem sırasında oluşturulan özel durumları yakalamak için, görev sınıfını kullanın ve hata işleme Devamı ekleyin. Hata işleme devamı, diğer iş parçacıklarında oluşturulan özel durumları çağıran iş parçacığına geri gönderir, böylece kodunuzda yalnızca bir noktada tüm olası özel durumları işleyebilmenizi sağlayabilirsiniz. Daha fazla bilgi için bkz. [zaman uyumsuz C++programlama ](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps).

## <a name="unhandlederrordetected-event"></a>Unhandlederroralgılanan olay

Windows 8.1, [Windows:: ApplicationModel:: Core:: CoreApplication:: Unhandlederroralgılanan](/uwp/api/windows.applicationmodel.core.icoreapplicationunhandlederror.unhandlederrordetected) statik olaya abone olabilir ve bu işlem, işlemi çıkarmak üzere işlenmemiş hatalara erişim sağlar. Hatanın kaynaklandığı durumlar ne olursa olsun, bu işleyiciye olay bağımsız değişkenleri ile geçirilen bir [Windows:: ApplicationModel:: Core:: Unhandlebir](/uwp/api/windows.applicationmodel.core.unhandlederror) Object nesnesi olarak ulaşır. Nesnesi üzerinde çağırdığınızda `Propagate` , hata koduna karşılık gelen türden bir `Platform::*Exception` oluşturur ve atar. Catch blokları ' nda, gerekirse Kullanıcı durumunu kaydedebilir ve sonra işlemi çağırarak `throw`işlemin sonlandırılmasına izin verebilir ya da programı bilinen bir duruma geri almak için bir şey yapabilirsiniz. Aşağıdaki örnekte temel desenler gösterilmektedir:

App. xaml. h içinde:

```cpp
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);
```

App. xaml. cpp içinde:

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

C++/CX `finally` yan tümcesini kullanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[C++/CX Dil Başvurusu](visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](namespaces-reference-c-cx.md)
