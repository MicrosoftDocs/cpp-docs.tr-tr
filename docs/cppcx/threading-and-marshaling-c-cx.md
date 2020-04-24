---
title: İş Parçacığı Oluşturma ve Hazırlama (C++/CX)
ms.date: 12/30/2016
f1_keywords:
- C4451
helpviewer_keywords:
- threading issues, C++/CX
- agility, C++/CX
- C++/CX, threading issues
ms.assetid: 83e9ca1d-5107-4194-ae6f-e01bd928c614
ms.openlocfilehash: 6b57366df5f466ffe49e4c0b46e05b1eed515535
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032492"
---
# <a name="threading-and-marshaling-ccx"></a>İş Parçacığı Oluşturma ve Hazırlama (C++/CX)

Durumların büyük çoğunluğunda, standart C++ nesneleri gibi Windows Runtime sınıflarının örneklerine herhangi bir iş parçacığından erişilebilir. Bu tür sınıflar "çevik" olarak adlandırılır. Ancak, Windows ile birlikte gönderi yapan az sayıdawindows Runtime sınıfı çevik değildir ve standart C++ nesnelerinden çok COM nesneleri gibi tüketilmelidir. Çevik olmayan sınıfları kullanmak için com uzmanı olmanız gerekmez, ancak sınıfın iş parçacığı modelini ve mareşaldavranışını göz önünde bulundurmanız gerekir. Bu makalede, çevik olmayan bir sınıf örneğini tüketmeniz gereken nadir senaryolar için arka plan ve kılavuz sağlar.

## <a name="threading-model-and-marshaling-behavior"></a>İş parçacığı modeli ve mareşaldavranışı

Windows Runtime sınıfı, uygulanan iki öznitelikte belirtildiği gibi, eşzamanlı iş parçacığı erişimini çeşitli şekillerde destekleyebilir:

- `ThreadingModel`öznitelik, numaralandırma tarafından `ThreadingModel` tanımlandığı gibi STA, MTA veya Her Ikisi gibi değerlerden birine sahip olabilir.

- `MarshallingBehavior`öznitelik, numaralandırma tarafından `MarshallingType` tanımlanan Çevik, Yok veya Standart değerlerinden birine sahip olabilir.

Öznitelik, `ThreadingModel` etkinleştirildiğinde sınıfın nerede yüklendiğini belirtir: yalnızca bir kullanıcı arabirimi iş parçacığı (STA) bağlamında, yalnızca bir arka plan iş parçacığı (MTA) bağlamında veya nesneyi oluşturan iş parçacığı bağlamında (Her ikisi) belirtilir. Öznitelik değerleri, `MarshallingBehavior` nesnenin çeşitli iş parçacığı bağlamlarında nasıl nasıl hissettiğini ifade eder; çoğu durumda, bu değerleri ayrıntılı olarak anlamak zorunda değilsiniz.  Windows API tarafından sağlanan sınıfların yaklaşık yüzde 90'ı `MarshallingType`=Her ikisine ve =Çevik'e sahiptir. `ThreadingModel` Bu, düşük düzeyli iş parçacığı ayrıntılarını saydam ve verimli bir şekilde işleyebilirler anlamına gelir.   "Çevik" `ref new` bir sınıf oluşturmak için kullandığınızda, bu sınıfüzerindeki yöntemleri ana uygulama iş parçacığınızdan veya bir veya daha fazla alt iş parçacığından arayabilirsiniz.  Başka bir deyişle, kodunuzun herhangi bir yerinden, Windows veya üçüncü bir taraf tarafından sağlanan olsun, çevik bir sınıf kullanabilirsiniz. Sınıfın iş parçacığı modeli veya mareşaldavranışı ile ilgili olmak zorunda değilsiniz.

## <a name="consuming-windows-runtime-components"></a>Windows Runtime bileşenlerini tüketme

Evrensel Bir Windows Platformu uygulaması oluşturduğunuzda, hem çevik hem de çevik olmayan bileşenlerle etkileşim kurabilirsiniz. Çevik olmayan bileşenlerle etkileşimkurduğunuzda, aşağıdaki uyarıyla karşılaşabilirsiniz.

### <a name="compiler-warning-c4451-when-consuming-non-agile-classes"></a>Çevik olmayan sınıfları tüketirken Derleyici uyarısı C4451

Çeşitli nedenlerden dolayı, bazı sınıflar çevik olamaz. Hem kullanıcı arabirimi iş parçacığından hem de arka plan iş parçacığından çevik olmayan sınıförneklerine erişiyorsanız, çalışma zamanında doğru davranışı sağlamak için ekstra özen sağlayın. Microsoft C++ derleyicisi, uygulamanızda genel kapsamda çevik olmayan bir çalışma zamanı sınıfını anında anladığınızda veya kendisi çevik olarak işaretlenmiş bir ref sınıfında çevik olmayan bir türü sınıf üyesi olarak beyan ettiğinizde uyarılar yayınlar.

Çevik olmayan sınıflar arasında, başa çıkmak en kolay olanlar `ThreadingModel`=Her `MarshallingType`ikisi ve =Standart vardır.  Bu sınıfları sadece `Agile<T>` yardımcı sınıfını kullanarak çevik yapabilirsiniz.   Aşağıdaki örnek, çevik olmayan bir tür `Windows::Security::Credentials::UI::CredentialPickerOptions^`nesnenin bildirimini ve sonuç olarak verilen derleyici uyarısını gösterir.

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

İşte yayınlanan uyarı:

> `Warning 1 warning C4451: 'Platform::Agile<T>::_object' : Usage of ref class 'Windows::Security::Credentials::UI::CredentialPickerOptions' inside this context can lead to invalid marshaling of object across contexts. Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead`

Üye kapsamıveya genel kapsamda bir başvuru eklediğinizde- "Standart" bir mareşaldavranışı olan bir nesneye, derleyici türü kaydırmanızı `Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead` tavsiye `Agile<T>`eden bir uyarı `Platform::Agile<T>`yayınlar: Eğer kullanırsanız, sınıfı diğer çevik sınıfgibi tüketebilirsiniz. Bu `Platform::Agile<T>` durumlarda kullanın:

- Çevik olmayan değişken genel kapsamda bildirilir.

- Çevik olmayan değişken sınıf kapsamında bildirilir ve alıcı kodun işaretçiyi kaçırma olasılığı vardır, yani doğru bir şekilde işaretçi olmadan farklı bir dairede kullanabilirsiniz.

Bu koşullardan hiçbiri geçerli değilse, içeren sınıfı çevik olmayan olarak işaretleyebilirsiniz. Başka bir deyişle, çevik olmayan nesneleri yalnızca çevik olmayan sınıflarda doğrudan tutmalı ve Platform:Çevik\<T> aracılığıyla çevik olmayan nesneleri çevik sınıflarda tutmalısınız.

Aşağıdaki örnek, uyarıyı `Agile<T>` güvenle yoksayabilmeniz için nasıl kullanılacağını gösterir.

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

Ref `Agile` sınıfında iade değeri veya parametre olarak geçirilemeyeceğine dikkat edin. Yöntem, `Agile<T>::Get()` ortak bir yöntemde veya özellikte uygulama ikili arabirimi (ABI) üzerinden geçebileceğiniz bir işbaşı-nesne (^) döndürür.

"Yok" bir mareşal davranışı olan bir in-proc Windows Runtime sınıfına bir başvuru oluşturduğunuzda, derleyici C4451 uyarı sorunları ama kullanmayı `Platform::Agile<T>`düşünün önermez .  Derleyici bu uyarının ötesinde herhangi bir yardım sunamaz, bu nedenle sınıfı doğru kullanmak ve kodunuzun STA bileşenlerini yalnızca kullanıcı arabirimi iş parçacığından ve MTA bileşenlerini yalnızca bir arka plan iş parçacığından aramasını sağlamak sizin sorumluluğunuzdadır.

## <a name="authoring-agile-windows-runtime-components"></a>Çevik Windows Runtime bileşenleriyazma

C++/CX'te bir ref sınıfı tanımladığınızda, varsayılan olarak çeviktir,yani `ThreadingModel`=Her `MarshallingType`ikisi ve =Çevik vardır.  Windows Runtime C++ Şablon Kitaplığı kullanıyorsanız, '' dan ' ' `FtmBase`ı kullanarak `FreeThreadedMarshaller`sınıfınızı çevik hale getirebilirsiniz.  =Her ikisi veya `ThreadingModel` `ThreadingModel`=MTA'sı olan bir sınıf yazarsanız, sınıfın iş parçacığı için güvenli olduğundan emin olun.

İş parçacığı modelini ve bir ref sınıfının mareşaldavranışını değiştirebilirsiniz. Ancak, sınıfı çevik olmayan hale getiren değişiklikler yaparsanız, bu değişikliklerle ilişkili etkileri anlamanız gerekir.

Aşağıdaki örnek, Windows `MarshalingBehavior` Runtime sınıf kitaplığında nasıl uygulanacağı ve `ThreadingModel` çalışma zamanı sınıfına nasıl atfedilenleri gösterir. Bir uygulama DLL'yi kullandığında ve `ref new` bir `MySTAClass` sınıf nesnesini etkinleştirmek için anahtar sözcüğü kullandığında, nesne tek iş parçacığı bir dairede etkinleştirilir ve mareşalliği desteklemez.

```
using namespace Windows::Foundation::Metadata;
using namespace Platform;

[Threading(ThreadingModel::STA)]
[MarshalingBehavior(MarshalingType::None)]
public ref class MySTAClass
{
};
```

Kapalı bir sınıfın, derleyicinin türemiş sınıfların bu öznitelikler için aynı değere sahip olduğunu doğrulayabilmesi için, bağlama ve iş parçacığı öznitelik ayarlarına sahip olması gerekir. Sınıf ayarları açıkça ayarlı değilse, derleyici bir hata oluşturur ve derlemek için başarısız olur. Mühürsüz bir sınıftan türetilen herhangi bir sınıf, bu durumlardan herhangi birinde derleyici hatası oluşturur:

- Ve `ThreadingModel` `MarshallingBehavior` öznitelikleri türemiş sınıfta tanımlı değildir.

- Türemiş `ThreadingModel` sınıftaki özniteliklerin `MarshallingBehavior` değerleri taban sınıftakilerle eşleşmiyor.

Üçüncü taraf bir Windows Runtime bileşeni tarafından gerekli olan iş parçacığı ve düzenleme bilgileri, bileşeniçin uygulama bildirimi kayıt bilgilerinde belirtilir. Tüm Windows Runtime bileşenlerinizi çevik yapmanızı öneririz. Bu, istemci kodunun bileşeninizi uygulamadaki herhangi bir iş parçacığından aramasını sağlar ve bu çağrıların performansını artırır, çünkü bunlar doğrudan aramalardır. Sınıfınızı bu şekilde yazarsanız, istemci kodu sınıfınızı `Platform::Agile<T>` tüketmek için kullanmak zorunda değildir.

## <a name="see-also"></a>Ayrıca bkz.

[ThreadingModel](/uwp/api/windows.foundation.metadata.threadingmodel)<br/>
[MarshallingDavranışı](/uwp/api/windows.foundation.metadata.marshalingbehaviorattribute)
