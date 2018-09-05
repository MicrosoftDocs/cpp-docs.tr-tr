---
title: İş parçacığı oluşturma ve sıralama (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- C4451
helpviewer_keywords:
- threading issues, C++/CX
- agility, C++/CX
- C++/CX, threading issues
ms.assetid: 83e9ca1d-5107-4194-ae6f-e01bd928c614
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4cf37857e12eb795ebfa4c5c115bc80a1688d69e
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43677158"
---
# <a name="threading-and-marshaling-ccx"></a>İş parçacığı oluşturma ve sıralama (C + +/ CX)
Çalışmaları büyük çoğunluğu, standart C++ nesneleri gibi Windows çalışma zamanı sınıfların örneklerini herhangi bir iş parçacığından erişilebilir. Bu tür sınıflar için "Çevik" adlandırılır. Ancak, Windows ile birlikte Windows çalışma zamanı sınıflar az sayıda Çevik olmayan ve standart C++ nesnelerden COM nesneleri gibi daha kullanılması gerekir. Çevik olmayan sınıflarını kullanmak için bir COM uzman olmanız gerekmez, ancak bu sınıfın iş parçacığı modeli ve sıralama davranışını dikkate almak gerekir. Bu makalede, arka plan ve Çevik olmayan bir sınıf örneği kullanmak gereken bu nadir senaryoları için yönergeler sağlar.  
  
## <a name="threading-model-and-marshaling-behavior"></a>İş parçacığı modeli ve hazırlama davranışı  
 Bir Windows çalışma zamanı sınıf eşzamanlı iş parçacığı erişim uygulanmış bir iki özniteliği tarafından belirtildiği gibi çeşitli şekillerde destekleyebilirsiniz:  
  
-   `ThreadingModel` öznitelik değerlerden biri olabilir: STA, MTA, veya her ikisi de tarafından tanımlandığı gibi `ThreadingModel` sabit listesi.  
  
-   `MarshallingBehavior` özniteliği değerlerden biri olabilir: hiçbiri, Çevik veya tarafından tanımlanan standart `MarshallingType` numaralandırması.  
  
 `ThreadingModel` Özniteliği, sınıf etkinleştirildiğinde yüklendiği belirtir: yalnızca bir kullanıcı arabirimi iş parçacığı (STA) bağlamında, bir arka plan iş parçacığı (MTA) bağlamında yalnızca veya iş parçacığının bağlamında, nesneyi (her ikisi de) oluşturur. `MarshallingBehavior` Öznitelik değerleri bakın nesne iş parçacığı çeşitli bağlamlarda nasıl davranacağını için; çoğu durumda, bu değerleri ayrıntılı anlamak zorunda değilsiniz.  Windows API'sı tarafından sağlanan sınıfları yaklaşık yüzde 90'sahip `ThreadingModel`hem = ve `MarshallingType`Çevik =. Bu, alt düzey bir iş parçacığı ayrıntıları şeffaf ve verimli bir şekilde işleyebileceğini anlamına gelir.   Kullanırken `ref new` "Çevik" bir sınıf oluşturmak için yöntemleri üzerinde ana uygulama iş parçacığı veya bir veya daha fazla çalışan iş parçacıkları çağırabilirsiniz.  Diğer bir deyişle, Çevik bir sınıfı kullanabilirsiniz — olup, Windows veya üçüncü taraf tarafından sağlanan ne olursa olsun — her yerden kod. Sınıfın iş parçacığı modeli veya davranışını sıralama ile önceliğiniz olması gerekmez.  
  
## <a name="consuming-windows-runtime-components"></a>Windows çalışma zamanı bileşenlerini kullanma  
 Bir evrensel Windows platformu uygulaması oluşturduğunuzda, Çevik ve Çevik olmayan bileşenleri ile etkileşim. Çevik olmayan bileşenleri ile etkileşim kurduğunuzda, aşağıdaki uyarıyı karşılaşabilirsiniz.  
  
### <a name="compiler-warning-when-consuming-non-agile-classes-c4451"></a>Çevik olmayan sınıflar (C4451) tüketildiğinde derleyici uyarısı  
 Çeşitli nedenlerden dolayı bazı sınıflar Çevik olamaz. Çevik olmayan sınıfların örneklerini hem kullanıcı arabirimi iş parçacığı hem de arka plan iş parçacığı erişen ve ardından ek almak, çalışma zamanında doğru davranışı sağlamak dikkat edin. Genel kapsamda uygulamanızda Çevik olmayan bir çalışma zamanı sınıf örneği ya da bir sınıf üyesine başvuru sınıfı, kendisi de Çevik işaretlenir Çevik olmayan türünü bildirmesine Visual C++ Derleyici uyarı verir.  
  
 Çevik olmayan sınıflarını, kolay uğraşmanız sahip olan `ThreadingModel`hem = ve `MarshallingType`standart =.  Bu sınıfların Çevik yalnızca kullanarak yapabileceğiniz `Agile<T>` yardımcı sınıfı.   Aşağıdaki örnek, Çevik olmayan bir nesne türünün bildirimi gösterir `Windows::Security::Credentials::UI::CredentialPickerOptions^`ve sonuç olarak verilen bir derleyici uyarısı.  
  
```  
  
ref class MyOptions  
    {  
    public:  
        property Windows::Security::Credentials::UI::CredentialPickerOptions^ Options  
  
        {  
            Windows::Security::Credentials::UI::CredentialPickerOptions^ get()   
            {  
                return _myOptions;  
            }  
        }  
    private:  
        Windows::Security::Credentials::UI::CredentialPickerOptions^ _myOptions;  
    };  
```  
  
 Verilen uyarı şu şekildedir:  
  
> `Warning 1 warning C4451: 'Platform::Agile<T>::_object' : Usage of ref class 'Windows::Security::Credentials::UI::CredentialPickerOptions' inside this context can lead to invalid marshaling of object across contexts. Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead`  
  
 Bir başvuru eklediğinizde — üye kapsamı veya genel kapsamlı — bir hazırlama davranışı "Standart" olan bir nesne için derleyici türüne sarın başlatmanızı öneren bir uyarı verir. `Platform::Agile<T>`: `Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead` kullanırsanız `Agile<T>`, sınıfın tüketebilir. Çevik herhangi bir sınıf gibi kullanabilirsiniz. Kullanım `Platform::Agile<T>` bu durumlarda:  
  
-   Çevik olmayan değişken genel kapsamda bildirilir.  
  
-   Çevik olmayan değişken sınıf kapsamında bildirilen ve kod tüketen işaretçi smuggle kaybedilebilir — diğer bir deyişle, doğru sıralama olmadan farklı bir grupta kullanın.  
  
 Ardından bu koşulların hiçbiri uygularsanız, Çevik olmayan olarak içerilen sınıf işaretleyebilirsiniz. Diğer bir deyişle, doğrudan Çevik olmayan nesneler yalnızca Çevik olmayan sınıflarda tutun ve gerekir Platform::Agile aracılığıyla Çevik olmayan nesneler tutun\<T > Çevik sınıflardaki.  
  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `Agile<T>` böylece bu uyarıyı güvenle yok sayabilirsiniz.  
  
```  
  
#include <agile.h>  
ref class MyOptions  
    {  
    public:  
        property Windows::Security::Credentials::UI::CredentialPickerOptions^ Options  
  
        {  
            Windows::Security::Credentials::UI::CredentialPickerOptions^ get()   
            {  
                return m_myOptions.Get();  
            }  
        }  
    private:  
        Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions^> m_myOptions;  
  
    };  
  
```  
  
 Dikkat `Agile` bir dönüş değeri veya bir başvuru sınıfının parametre olarak gönderilemez. `Agile<T>::Get()` Yöntemi, bir genel yöntem veya özellik bir tanıtıcı, uygulama ikili arabiriminde (ABI) geçirebileceğiniz nesne (^) döndürür.  
  
 Visual c++'da "None", sıralama davranışını bir işlemde Windows çalışma zamanı sınıf başvuru oluşturduğunuzda derleyici C4451 uyarı verir ancak kullanmayı düşünün önerisi olmayan `Platform::Agile<T>`.  Sınıf düzgün kullanın ve kodunuzun yalnızca bir arka plan iş parçacığından yalnızca kullanıcı arabirimi iş parçacığı bileşenlerini STA ve MTA bileşenleri çağıran emin olmak için sizin sorumluluğunuzdadır, bu nedenle, derleyici bu uyarıyı ötesinde herhangi bir yardım sunamazlar.  
  
## <a name="authoring-agile-windows-runtime-components"></a>Çevik Geliştirme Windows çalışma zamanı bileşenleri  
 Tanımladığınızda bir başvuru sınıfı C + +/ CX, onu varsayılan olarak Çevik — diğer bir deyişle, sahip `ThreadingModel`hem = ve `MarshallingType`Çevik =.  Windows çalışma zamanı C++ Şablon kitaplığı kullanıyorsanız, kendi sınıfınızı Çevik türeterek yapabileceğiniz `FtmBase`, kullanan `FreeThreadedMarshaller`.  Bir sınıf yazarsanız `ThreadingModel`hem = veya `ThreadingModel`MTA, = sınıf iş parçacığı açısından güvenli olduğundan emin olun.   
  
 İş parçacığı modeli ve bir başvuru sınıfının hazırlama davranışı değiştirebilirsiniz. Ancak, Çevik olmayan sınıf işleme değişiklikler yaparsanız, bu değişikliklerle ilişkili etkilerini anlamanız gerekir.  
  
 Aşağıdaki örnek nasıl uygulanacağını gösterir `MarshalingBehavior` ve `ThreadingModel` bir Windows çalışma zamanı Sınıf Kitaplığı'nda bir çalışma zamanı sınıf öznitelikleri. Ne zaman uygulama DLL kullanır ve kullandığı `ref new` etkinleştirmek için anahtar sözcüğü bir `MySTAClass` sınıfı nesne, nesnenin bir tek iş parçacıklı apartmanda etkinleştirilir ve hazırlama desteklemiyor.  
  
```  
using namespace Windows::Foundation::Metadata;  
using namespace Platform;  
  
[Threading(ThreadingModel::STA)]  
[MarshalingBehavior(MarshalingType::None)]   
public ref class MySTAClass  
{  
};  
  
```  
 
 Derleyici türetilen sınıfların bu öznitelikler için aynı değere sahip olduğunu doğrulayabilir hazırlama ve iş parçacığı oluşturma özniteliği ayarları korumasız bir sınıf olmalıdır. Sınıfı açıkça ayarları sahip değilse, derleyici bir hata oluşturur ve derlenemiyor. Bir unsealedclass türetilmiş herhangi bir sınıf ya da bu durumlarda bir derleyici hatası oluşturur:  
  
-   `ThreadingModel` Ve `MarshallingBehavior` öznitelikleri türetilmiş sınıf içinde tanımlı değil.  
  
-   Değerlerini `ThreadingModel` ve `MarshallingBehavior` türetilmiş sınıf özniteliklerinde bu temel sınıfta eşleşmiyor.  
  
 İş parçacığı oluşturma ve bir üçüncü taraf Windows çalışma zamanı bileşeni tarafından gerekli olan bilgileri hazırlama bileşeni için uygulama bildirim kayıt bilgileri belirtildi. Uygulamanızı Windows çalışma zamanı bileşenlerinin tümünü Çevik yapmanızı öneririz. Bu, istemci kodu bileşeniniz uygulamadaki herhangi bir iş parçacığı çağrı yapabilir ve herhangi bir sıralama sahip doğrudan çağrıları olduklarından bu çağrıları performansını artırır sağlar. Bu şekilde sınıfınızda Yazar sonra kullanmak istemci kodu yoksa `Platform::Agile<T>` sınıfınıza kullanma.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ThreadingModel](https://msdn.microsoft.com/library/windows/apps/xaml/windows.foundation.metadata.threadingmodel.aspx)   
 [MarshallingBehavior](https://msdn.microsoft.com/library/windows/apps/xaml/windows.foundation.metadata.marshalingbehaviorattribute.aspx)