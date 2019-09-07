---
title: İş parçacığı oluşturma veC++hazırlama (/CX)
ms.date: 12/30/2016
f1_keywords:
- C4451
helpviewer_keywords:
- threading issues, C++/CX
- agility, C++/CX
- C++/CX, threading issues
ms.assetid: 83e9ca1d-5107-4194-ae6f-e01bd928c614
ms.openlocfilehash: 05601367b6907e34d9d67364d35988a37ceae40c
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741121"
---
# <a name="threading-and-marshaling-ccx"></a>İş parçacığı oluşturma veC++hazırlama (/CX)

Çoğu durumda, standart C++ nesneler gibi Windows çalışma zamanı sınıf örneklerine herhangi bir iş parçacığından erişilebilir. Bu tür sınıflar "çevik" olarak adlandırılır. Ancak, Windows ile birlikte gelen çok sayıda Windows Çalışma Zamanı sınıfı çevik değildir ve standart C++ nesnelerden com nesneleri gibi daha fazla tükemelidir. Çevik olmayan sınıfları kullanmak için bir COM uzmanı olmanız gerekmez, ancak sınıfın iş parçacığı modelini ve sıralama davranışını dikkate almanız gerekir. Bu makalede, çevik olmayan bir sınıfın örneğini kullanmanız gereken nadir senaryolar için arka plan ve kılavuz sağlanmaktadır.

## <a name="threading-model-and-marshaling-behavior"></a>İş parçacığı modeli ve sıralama davranışı

Bir Windows Çalışma Zamanı sınıfı, uygulanan iki öznitelik tarafından belirtildiği gibi çeşitli yollarla eşzamanlı iş parçacığı erişimini destekleyebilir:

- `ThreadingModel`öznitelik, `ThreadingModel` numaralandırma tarafından tanımlanan bir değerden birine (STA, MTA veya her ikisi birden) sahip olabilir.

- `MarshallingBehavior`öznitelik, `MarshallingType` sabit listesi tarafından tanımlanan çevik, yok veya standart değerlerinden birine sahip olabilir.

`ThreadingModel` Öznitelik, etkinleştirildiğinde sınıfın nereye yükleneceğini belirtir: yalnızca bir kullanıcı arabirimi iş parçacığı (STA) bağlamında, yalnızca bir arka plan iş parçacığı (MTA) bağlamında veya nesneyi oluşturan iş parçacığı bağlamında (her ikisi de). `MarshallingBehavior` Öznitelik değerleri nesnenin çeşitli iş parçacığı bağlamlarında nasıl davrandığını ifade eder; çoğu durumda, bu değerleri ayrıntılı olarak anlamanız gerekmez.  Windows API tarafından sunulan sınıfların yüzde 90 ' i ve `ThreadingModel` `MarshallingType`= çevik ' i vardır. Bu, düşük düzeyli iş parçacığı ayrıntılarını saydam ve verimli bir şekilde işleyebilecekleri anlamına gelir.   "Çevik" `ref new` bir sınıf oluşturmak için kullandığınızda, ana uygulama iş parçacığınızdan veya bir ya da daha fazla çalışan iş parçacığından bu yöntem üzerinde yöntemler çağırabilirsiniz.  Diğer bir deyişle, kodunuzun herhangi bir yerinden Windows veya üçüncü taraf tarafından sağlanmadığına bakılmaksızın çevik bir sınıf kullanabilirsiniz. Sınıfın iş parçacığı modeli veya sıralama davranışına endişelenmeniz gerekmez.

## <a name="consuming-windows-runtime-components"></a>Windows Çalışma Zamanı bileşenleri kullanma

Bir Evrensel Windows Platformu uygulaması oluşturduğunuzda, hem çevik hem de çevik olmayan bileşenlerle etkileşim kurabilirsiniz. Çevik olmayan bileşenlerle etkileşim kurarken, aşağıdaki uyarıyla karşılaşabilirsiniz.

### <a name="compiler-warning-c4451-when-consuming-non-agile-classes"></a>Çevik olmayan sınıfları tükettiği zaman derleyici uyarısı C4451

Çeşitli nedenlerle bazı sınıflar çevik olamaz. Hem bir kullanıcı arabirimi iş parçacığından hem de bir arka plan iş parçacığından çevik olmayan sınıfların örneklerine erişiyorsanız, çalışma zamanında doğru davranışı sağlamak için ek bir işlem yapın. Microsoft C++ derleyicisi, uygulamanızda genel kapsamda çevik olmayan bir çalışma zamanı sınıfı örneklediğinizde veya çevik olmayan bir türü bir başvuru sınıfında kendisini çevik olarak işaretlenen bir sınıf üyesi olarak bildirmenizin bir uyarı verir.

Çevik olmayan sınıfların, en kolay `ThreadingModel`= ve `MarshallingType`= standart olan.  `Agile<T>` Yardımcı sınıfını kullanarak bu sınıfların çevik olmasını sağlayabilirsiniz.   Aşağıdaki örnek, türünde `Windows::Security::Credentials::UI::CredentialPickerOptions^`çevik olmayan bir nesnenin bir bildirimini ve sonuç olarak verilen derleyici uyarısını gösterir.

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

Verilen uyarı aşağıda verilmiştir:

> `Warning 1 warning C4451: 'Platform::Agile<T>::_object' : Usage of ref class 'Windows::Security::Credentials::UI::CredentialPickerOptions' inside this context can lead to invalid marshaling of object across contexts. Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead`

Üye kapsamında veya genel kapsamda — "standart" sıralama davranışına sahip bir nesneye bir başvuru eklediğinizde, derleyici, türü içine `Platform::Agile<T>`kaydıraöneren bir uyarı verir: `Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead``Agile<T>`Kullanıyorsanız, başka bir çevik sınıf gibi sınıfını kullanabilirsiniz. Bu `Platform::Agile<T>` koşullarda kullanın:

- Çevik olmayan değişken genel kapsamda bildirilmiştir.

- Çevik olmayan değişken sınıf kapsamında bildirilmiştir ve kodun kullanımı, işaretçiyi doğru sıralama olmadan farklı bir grupta kullanmak gibi bir şansınız olabilir.

Bu koşulların hiçbiri geçerli değilse, kapsayan sınıfı çevik olmayan olarak işaretleyebilirsiniz. Diğer bir deyişle, çevik olmayan nesneleri doğrudan çevik olmayan sınıflarda tutamaz ve çevik sınıflarda Platform:: çevik\<T > aracılığıyla çevik olmayan nesneleri tutabilmelisiniz.

Aşağıdaki örnek, uyarıyı güvenle yoksayabilmeniz `Agile<T>` için nasıl kullanılacağını gösterir.

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

`Agile` Başvuru sınıfında bir dönüş değeri veya parametresi olarak geçirilemediğine dikkat edin. Yöntemi `Agile<T>::Get()` , bir genel yöntem veya özellikte uygulama ikili arabirimi (ABI) üzerinden geçirebilmeniz için bir işleyici (^) döndürür.

"None" öğesinin sıralama davranışına sahip bir proc Windows Çalışma Zamanı sınıfına bir başvuru oluşturduğunuzda, derleyici uyarı C4451 sorun ancak kullanmayı `Platform::Agile<T>`düşünmenizi önermez.  Derleyici bu uyarının ötesinde herhangi bir yardım sunmamaktadır, bu nedenle sınıfı doğru şekilde kullanmak ve kodunuzun yalnızca kullanıcı arabirimi iş parçacığından ve MTA bileşenlerinden yalnızca bir arka plan iş parçacığından STA bileşenlerini çağırması gerekir.

## <a name="authoring-agile-windows-runtime-components"></a>Çevik Windows Çalışma Zamanı bileşenleri yazma

/CX içinde C++bir başvuru sınıfı tanımladığınızda, varsayılan olarak çevik olur; yani, `ThreadingModel`= ve `MarshallingType`çevik olur.  Windows çalışma zamanı C++ şablon kitaplığını kullanıyorsanız, sınıfından türeterek `FtmBase` `FreeThreadedMarshaller`sınıfınızı çevik hale getirebilirsiniz.  `ThreadingModel`= Ya da `ThreadingModel`= MTA içeren bir sınıf yazardıysanız, sınıfın iş parçacığı açısından güvenli olduğundan emin olun.

Bir başvuru sınıfının iş parçacığı modelini ve sıralama davranışını değiştirebilirsiniz. Ancak, sınıfı çevik olmayan bir şekilde işleyen değişiklikler yaparsanız, bu değişikliklerle ilişkili etkileri anlamanız gerekir.

Aşağıdaki örnek, bir Windows çalışma zamanı sınıf kitaplığındaki `MarshalingBehavior` çalışma `ThreadingModel` zamanı sınıfına ve özniteliklerin nasıl uygulanacağını gösterir. Bir uygulama dll 'i kullandığında ve bir `ref new` `MySTAClass` sınıf nesnesini etkinleştirmek için anahtar sözcüğünü kullandığında, nesne tek iş parçacıklı bir grupta etkinleştirilir ve sıralama desteklenmez.

```
using namespace Windows::Foundation::Metadata;
using namespace Platform;

[Threading(ThreadingModel::STA)]
[MarshalingBehavior(MarshalingType::None)]
public ref class MySTAClass
{
};
```

Korumasız bir sınıf, türetilmiş sınıfların bu öznitelikler için aynı değere sahip olduğunu doğrulayabilmesi için sıralama ve iş parçacığı oluşturma özniteliği ayarlarına sahip olmalıdır. Sınıfın ayarları açıkça ayarlanmamışsa, derleyici bir hata oluşturur ve derleme başarısız olur. Bir unduledclass sınıfından türetilmiş herhangi bir sınıf, bu durumların her birinde bir derleyici hatası oluşturur:

- `ThreadingModel` Ve`MarshallingBehavior` öznitelikleri türetilmiş sınıfta tanımlı değil.

- Türetilmiş sınıftaki `ThreadingModel` ve `MarshallingBehavior` özniteliklerinin değerleri, taban sınıfındakilerle eşleşmiyor.

Üçüncü taraf Windows Çalışma Zamanı bileşeni için gereken iş parçacığı oluşturma ve sıralama bilgileri, bileşen için uygulama bildirimi kayıt bilgilerinde belirtilmiştir. Tüm Windows Çalışma Zamanı bileşenlerinizi çevik yapmanızı öneririz. Bu, istemci kodunun uygulamanızı uygulamadaki herhangi bir iş parçacığından çağırabilmesini sağlar ve bu çağrıların performansını artırır çünkü sıralama olmayan doğrudan çağrılar olur. Sınıfınızı bu şekilde yazarsa, istemci kodunun sınıfınızı tüketmek için kullanmak `Platform::Agile<T>` zorunda değildir.

## <a name="see-also"></a>Ayrıca bkz.

[ThreadingModel](/uwp/api/Windows.Foundation.Metadata.ThreadingModel)<br/>
[Sıralamada Allingbehavior](/uwp/api/windows.foundation.metadata.marshalingbehaviorattribute)
