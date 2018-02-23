---
title: "İş parçacığı oluşturma ve sıralama (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- C4451
helpviewer_keywords:
- threading issues, C++/CX
- agility, C++/CX
- C++/CX, threading issues
ms.assetid: 83e9ca1d-5107-4194-ae6f-e01bd928c614
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9b1544f18d0d5206e178cf42705d9567fad2423c
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="threading-and-marshaling-ccx"></a>İş parçacığı oluşturma ve sıralama (C + +/ CX)
Durumları büyük çoğunluğu herhangi bir iş parçacığından standart C++ nesneleri gibi Windows çalışma zamanı sınıfların örneklerini erişilebilir. Bu tür sınıflar olarak "Çevik" denir. Ancak, Windows ile birlikte Windows çalışma zamanı sınıfları az sayıda Çevik olmayan ve daha fazla standart C++ nesneleri daha COM nesneleri gibi kullanılması gerekir. Çevik olmayan sınıflarını kullanmak için bir COM uzman olması gerekmez, ancak sınıfın iş parçacığı modelini ve hazırlama davranışını dikkate gerekir. Bu makale, arka plan ve Çevik olmayan sınıfının bir örneğini kullanmak gereken bu nadir senaryoları için yönergeler sağlar.  
  
## <a name="threading-model-and-marshaling-behavior"></a>Modeli iş parçacığı oluşturma ve hazırlama davranışı  
 Windows çalışma zamanı sınıfı eşzamanlı iş parçacığı erişim uygulanmış iki öznitelik belirtildiği gibi çeşitli şekillerde destekleyebilirsiniz:  
  
-   `ThreadingModel` öznitelik değerlerden biri olabilir — STA, MTA, ya da her ikisini tarafından tanımlanan `ThreadingModel` numaralandırması.  
  
-   `MarshallingBehavior` öznitelik değerlerden biri olabilir: None, Çevik veya tarafından tanımlanan standart `MarshallingType` numaralandırması.  
  
 `ThreadingModel` Özniteliği, sınıf etkinleştirildiğinde yüklendiği belirtir: yalnızca bir kullanıcı arabirimi iş parçacığı (STA) bağlamında, yalnızca bir arka plan iş parçacığı (MTA) içerik veya iş parçacığının bağlamında nesne (her ikisi de) oluşturur. `MarshallingBehavior` Öznitelik değerleri başvurmak nesne çeşitli iş parçacığı bağlamlarda biçimini; çoğu durumda, bu değerleri ayrıntılı anlamak zorunda değilsiniz.  Windows API tarafından sağlanan sınıflarını yaklaşık yüzde 90'ından sahip `ThreadingModel`her ikisi de = ve `MarshallingType`Çevik =. Bu, alt düzey iş parçacığı ayrıntıları saydam ve verimli bir şekilde işleyebileceğini anlamına gelir.   Kullandığınızda `ref new` "Çevik" bir sınıf oluşturmak için yöntemleri üzerinde ana uygulama iş parçacığı ya da bir veya daha fazla çalışan iş parçacığı çağırabilirsiniz.  Diğer bir deyişle, Çevik sınıfı kullanabilirsiniz — olup, Windows veya bir üçüncü taraf tarafından sağlanan olsun — her yerden, kodunuzda. Sınıfın iş parçacığı modeli veya hazırlama davranışı ile endişelenmeniz gerekmez.  
  
## <a name="consuming-windows-runtime-components"></a>Windows çalışma zamanı bileşenleri kullanma  
 Bir evrensel Windows Platform uygulaması oluşturduğunuzda, Çevik ve Çevik olmayan bileşenlerle etkileşimli. Çevik olmayan bileşenleri ile etkileşim kurduklarında, aşağıdaki uyarıyı karşılaşabilirsiniz.  
  
### <a name="compiler-warning-when-consuming-non-agile-classes-c4451"></a>Çevik olmayan sınıfları (C4451) kullanırken derleyici uyarısı  
 Çeşitli nedenlerle bazı sınıfları Çevik olamaz. Çalışma zamanında doğru davranışı sağlamak bir kullanıcı arabirimi iş parçacığı hem bir arka plan iş parçacığı Çevik olmayan sınıfların örneklerini erişen ve ardından ek ele kullanırsanız dikkatli olun. Genel kapsamlı uygulamanızda Çevik olmayan bir çalışma zamanı sınıf örneği veya sınıf üyesine bir başvuru sınıf, kendisini olarak Çevik işaretlenir Çevik olmayan türünü bildirmesine olduğunda Visual C++ derleyici uyarıları yayınlar.  
  
 Çevik olmayan sınıflarını, kolay uğraşmanız olan olan `ThreadingModel`her ikisi de = ve `MarshallingType`standart =.  Bu sınıfların Çevik yalnızca kullanarak yapabileceğiniz `Agile<T>` yardımcı sınıfı.   Aşağıdaki örnek, Çevik olmayan bir nesne türü bildirimini gösterir `Windows::Security::Credentials::UI::CredentialPickerOptions^`ve sonuç olarak verilen derleyici uyarısı.  
  
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
  
 Verilen uyarı şöyledir:  
  
> `Warning 1 warning C4451: 'Platform::Agile<T>::_object' : Usage of ref class 'Windows::Security::Credentials::UI::CredentialPickerOptions' inside this context can lead to invalid marshaling of object across contexts. Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead`  
  
 Bir başvuru eklediğinizde — üye kapsam veya genel kapsam — hazırlama davranışı "Standart" olan bir nesneyi için derleyici türünde sarmalamak başlatmanızı öneren bir uyarı verir `Platform::Agile<T>`: `Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead` kullanırsanız `Agile<T>`, sınıf tüketebileceği Çevik herhangi bir sınıf gibi kullanabilirsiniz. Kullanım `Platform::Agile<T>` bu durumlarda:  
  
-   Çevik olmayan değişkeni genel kapsamda bildirildi.  
  
-   Çevik olmayan değişkeni sınıfı kapsamda bildirilmiş ve kod tüketen işaretçinin smuggle olasılığı yüksektir — diğer bir deyişle, doğru hazırlama olmadan farklı bir grupta kullanın.  
  
 Ardından bu koşulların hiçbiri uygularsanız, içeren sınıf Çevik dışı olarak işaretleyebilirsiniz. Diğer bir deyişle, doğrudan Çevik olmayan nesneler yalnızca Çevik olmayan sınıflarda tutun ve gerekir Platform::Agile aracılığıyla Çevik olmayan nesneler tutun\<T > Çevik sınıflardaki.  
  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `Agile<T>` böylece uyarıyı yok sayabilirsiniz.  
  
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
  
 Dikkat `Agile` bir dönüş değeri veya ref sınıfında parametre olarak gönderilemez. `Agile<T>::Get()` Yöntemi bir tanıtıcı-için-uygulama ikili arabirimi (ABI) geçirebileceğiniz nesnesini döndürür (^) bir ortak yöntemi veya özelliği.  
  
 Visual C++ ' ta, "None" hazırlama davranışı sahip bir işlem dışı Windows çalışma zamanı sınıf başvuru oluşturduğunuzda derleyici sorunları uyarı C4451 ancak kullanmayı düşünün önermek değil `Platform::Agile<T>`.  Sınıf doğru kullanın ve kodunuzu yalnızca bir arka plan iş parçacığından STA bileşenlerinden yalnızca kullanıcı arabirimi iş parçacığı ve MTA bileşenleri çağıran sağlamak için sizin sorumluluğunuzdadır olacak şekilde derleyici bu uyarıyı ötesinde herhangi bir yardım sunamazlar.  
  
## <a name="authoring-agile-windows-runtime-components"></a>Geliştirme Çevik Windows çalışma zamanı bileşenleri  
 Tanımladığınızda ref sınıfı C + +/ CX, onu varsayılan olarak Çevik — diğer bir deyişle, sahip `ThreadingModel`her ikisi de = ve `MarshallingType`Çevik =.  Kullanıyorsanız, [!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)], sınıfınız Çevik türetme tarafından yapabileceğiniz `FtmBase`, kullanan `FreeThreadedMarshaller`.  Olan bir sınıfı yazarsanız `ThreadingModel`her ikisi de = veya `ThreadingModel`MTA, = sınıfı iş parçacığı açısından güvenli olduğundan emin olun. Daha fazla bilgi için bkz: [oluşturma ve kullanma nesneleri (WRL)](http://msdn.microsoft.com/en-us/d5e42216-e888-4f1f-865a-b5ccd0def73e).  
  
 İş parçacığı modelini ve ref sınıfının hazırlama davranışı değiştirebilirsiniz. Ancak, sınıf Çevik olmayan işleme değişiklikler yapmak isterseniz, bu değişikliklerle ilişkili etkileri anlamanız gerekir.  
  
 Aşağıdaki örnekte nasıl uygulanacağını gösterir `MarshalingBehavior` ve `ThreadingModel` Windows çalışma zamanı Sınıf Kitaplığı'nda bir çalışma zamanı sınıf özniteliklerini. Ne zaman bir uygulama DLL, kullanır `ref new` etkinleştirmek için anahtar sözcüğü bir `MySTAClass` sınıfı nesne, nesne tek iş parçacıklı bir grupta etkinleştirilir ve hazırlama desteklemiyor.  
  
```  
using namespace Windows::Foundation::Metadata;  
using namespace Platform;  
  
[Threading(ThreadingModel::STA)]  
[MarshalingBehavior(MarshalingType::None)]   
public ref class MySTAClass  
{  
};  
  
```  
 
 Derleyici türetilen sınıflar bu öznitelikler için aynı değere sahip olduğunuzu doğrulayabilmeniz korumasız bir sınıf hazırlama ve iş parçacığı özniteliği ayarlara sahip olmalıdır. Sınıfı ayarları açıkça ayarlanmış yoksa, derleyici bir hata oluşturur ve derlemek başarısız olur. Derleyici Hatası bir unsealedclass türetilmiş herhangi bir sınıf bu gibi durumlarda birini oluşturur:  
  
-   `ThreadingModel` Ve `MarshallingBehavior` öznitelikleri türetilmiş sınıf içinde tanımlı değil.  
  
-   Değerlerini `ThreadingModel` ve `MarshallingBehavior` türetilmiş sınıf öznitelikleri temel sınıfı de eşleşmiyor.  
  
 İş parçacığı oluşturma ve bir üçüncü taraf Windows çalışma zamanı bileşeni tarafından gerekli olan bilgileri hazırlama bileşen için uygulama bildirimi kayıt bilgilerinin belirtilen. Tüm Windows çalışma zamanı bileşenlerini Çevik yaptığınız öneririz. Bu, istemci kodu bileşeniniz uygulamadaki tüm iş çağırabilir ve hiçbir hazırlama sahip doğrudan çağrılar oldukları için bu çağrıları performansını artırır sağlar. Bu şekilde sınıfınızda Yazar sonra kullanmak istemci kodu yoksa `Platform::Agile<T>` sınıfınız kullanmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ThreadingModel](http://msdn.microsoft.com/library/windows/apps/xaml/windows.foundation.metadata.threadingmodel.aspx)   
 [MarshallingBehavior](http://msdn.microsoft.com/library/windows/apps/xaml/windows.foundation.metadata.marshalingbehaviorattribute.aspx)