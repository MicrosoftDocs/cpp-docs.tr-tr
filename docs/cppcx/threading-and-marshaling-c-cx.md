---
description: 'Daha fazla bilgi edinin: Iş parçacığı oluşturma ve hazırlama (C++/CX)'
title: İş Parçacığı Oluşturma ve Hazırlama (C++/CX)
ms.date: 12/30/2016
f1_keywords:
- C4451
helpviewer_keywords:
- threading issues, C++/CX
- agility, C++/CX
- C++/CX, threading issues
ms.assetid: 83e9ca1d-5107-4194-ae6f-e01bd928c614
ms.openlocfilehash: 7ec045b4023e7c27ef55242af44e64033d40f056
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307606"
---
# <a name="threading-and-marshaling-ccx"></a>İş Parçacığı Oluşturma ve Hazırlama (C++/CX)

Çoğu durumda, standart C++ nesneleri gibi Windows Çalışma Zamanı sınıfların örneklerine herhangi bir iş parçacığından erişilebilir. Bu tür sınıflar "çevik" olarak adlandırılır. Ancak, Windows ile birlikte gelen küçük sayıda Windows Çalışma Zamanı sınıfı çevik değildir ve standart C++ nesnelerinden COM nesneleri gibi daha fazla kullanılmalıdır. Çevik olmayan sınıfları kullanmak için bir COM uzmanı olmanız gerekmez, ancak sınıfın iş parçacığı modelini ve sıralama davranışını dikkate almanız gerekir. Bu makalede, çevik olmayan bir sınıfın örneğini kullanmanız gereken nadir senaryolar için arka plan ve kılavuz sağlanmaktadır.

## <a name="threading-model-and-marshaling-behavior"></a>İş parçacığı modeli ve sıralama davranışı

Bir Windows Çalışma Zamanı sınıfı, uygulanan iki öznitelik tarafından belirtildiği gibi çeşitli yollarla eşzamanlı iş parçacığı erişimini destekleyebilir:

- `ThreadingModel` öznitelik, numaralandırma tarafından tanımlanan bir değerden birine (STA, MTA veya her Ikisi birden) sahip olabilir `ThreadingModel` .

- `MarshallingBehavior` öznitelik, sabit listesi tarafından tanımlanan çevik, yok veya standart değerlerinden birine sahip olabilir `MarshallingType` .

`ThreadingModel`Öznitelik, etkinleştirildiğinde sınıfın nereye yükleneceğini belirtir: yalnızca bir kullanıcı arabirimi iş parçacığı (STA) bağlamında, yalnızca bir arka plan iş parçacığı (MTA) bağlamında veya nesneyi oluşturan iş parçacığı bağlamında (her Ikisi de). `MarshallingBehavior`Öznitelik değerleri nesnenin çeşitli iş parçacığı bağlamlarında nasıl davrandığını ifade eder; çoğu durumda, bu değerleri ayrıntılı olarak anlamanız gerekmez.  Windows API tarafından sunulan sınıfların yüzde 90 ' i ve = çevik ' i vardır `ThreadingModel` `MarshallingType` . Bu, düşük düzeyli iş parçacığı ayrıntılarını saydam ve verimli bir şekilde işleyebilecekleri anlamına gelir.   `ref new`"Çevik" bir sınıf oluşturmak için kullandığınızda, ana uygulama iş parçacığınızdan veya bir ya da daha fazla çalışan iş parçacığından bu yöntem üzerinde yöntemler çağırabilirsiniz.  Diğer bir deyişle, kodunuzun herhangi bir yerinden Windows veya üçüncü taraf tarafından sağlanmadığına bakılmaksızın çevik bir sınıf kullanabilirsiniz. Sınıfın iş parçacığı modeli veya sıralama davranışına endişelenmeniz gerekmez.

## <a name="consuming-windows-runtime-components"></a>Windows Çalışma Zamanı bileşenleri kullanma

Bir Evrensel Windows Platformu uygulaması oluşturduğunuzda, hem çevik hem de çevik olmayan bileşenlerle etkileşim kurabilirsiniz. Çevik olmayan bileşenlerle etkileşim kurarken, aşağıdaki uyarıyla karşılaşabilirsiniz.

### <a name="compiler-warning-c4451-when-consuming-non-agile-classes"></a>Çevik olmayan sınıfları tükettiği zaman derleyici uyarısı C4451

Çeşitli nedenlerle bazı sınıflar çevik olamaz. Hem bir kullanıcı arabirimi iş parçacığından hem de bir arka plan iş parçacığından çevik olmayan sınıfların örneklerine erişiyorsanız, çalışma zamanında doğru davranışı sağlamak için ek bir işlem yapın. Microsoft C++ derleyicisi, uygulamanızda genel kapsamda çevik olmayan bir çalışma zamanı sınıfını örneklediğinizde veya çevik olmayan bir türü bir başvuru sınıfında kendisinin çevik olarak işaretlenmiş bir sınıf üyesi olarak bildirmenizin bir uyarı verir.

Çevik olmayan sınıfların, en kolay `ThreadingModel` = ve `MarshallingType` = Standart olan.  Yardımcı sınıfını kullanarak bu sınıfların çevik olmasını sağlayabilirsiniz `Agile<T>` .   Aşağıdaki örnek, türünde çevik olmayan bir nesnenin bir bildirimini `Windows::Security::Credentials::UI::CredentialPickerOptions^` ve sonuç olarak verilen derleyici uyarısını gösterir.

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

Üye kapsamında veya genel kapsamda — "standart" öğesinin sıralama davranışına sahip bir nesneye bir başvuru eklediğinizde, derleyici içinde türü sarması için size öneren bir uyarı yayınlar `Platform::Agile<T>` : kullanıyorsanız `Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead` `Agile<T>` , sınıfı diğer çevik sınıflar gibi kullanabilirsiniz. `Platform::Agile<T>`Bu koşullarda kullanın:

- Çevik olmayan değişken genel kapsamda bildirilmiştir.

- Çevik olmayan değişken sınıf kapsamında bildirilmiştir ve kodun kullanımı, işaretçiyi doğru sıralama olmadan farklı bir grupta kullanmak gibi bir şansınız olabilir.

Bu koşulların hiçbiri geçerli değilse, kapsayan sınıfı çevik olmayan olarak işaretleyebilirsiniz. Diğer bir deyişle, çevik olmayan nesneleri doğrudan çevik olmayan sınıflarda tutmanız ve çevik sınıflarda Platform:: çevik nesneleri aracılığıyla çevik olmayan nesneleri tutmanız gerekir \<T> .

Aşağıdaki örnek, `Agile<T>` uyarıyı güvenle yoksayabilmeniz için nasıl kullanılacağını gösterir.

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

`Agile`Başvuru sınıfında bir dönüş değeri veya parametresi olarak geçirilemediğine dikkat edin. `Agile<T>::Get()`Yöntemi, bir genel yöntem veya özellikte uygulama ikili arabirimi (ABI) üzerinden geçirebilmeniz için bir işleyici (^) döndürür.

"None" öğesinin sıralama davranışına sahip bir proc Windows Çalışma Zamanı sınıfına bir başvuru oluşturduğunuzda, derleyici uyarı C4451 sorun ancak kullanmayı düşünmenizi önermez `Platform::Agile<T>` .  Derleyici bu uyarının ötesinde herhangi bir yardım sunmamaktadır, bu nedenle sınıfı doğru şekilde kullanmak ve kodunuzun yalnızca kullanıcı arabirimi iş parçacığından ve MTA bileşenlerinden yalnızca bir arka plan iş parçacığından STA bileşenlerini çağırması gerekir.

## <a name="authoring-agile-windows-runtime-components"></a>Çevik Windows Çalışma Zamanı bileşenleri yazma

C++/CX ' te bir başvuru sınıfı tanımladığınızda, varsayılan olarak çevik olur; yani, `ThreadingModel` = ve `MarshallingType` çevik olur.  Windows Çalışma Zamanı C++ Şablon kitaplığı kullanıyorsanız, sınıfından türeterek sınıfınızı çevik hale getirebilirsiniz `FtmBase` `FreeThreadedMarshaller` .  `ThreadingModel`= Ya da = MTA içeren bir sınıf yazardıysanız `ThreadingModel` , sınıfın iş parçacığı açısından güvenli olduğundan emin olun.

Bir başvuru sınıfının iş parçacığı modelini ve sıralama davranışını değiştirebilirsiniz. Ancak, sınıfı çevik olmayan bir şekilde işleyen değişiklikler yaparsanız, bu değişikliklerle ilişkili etkileri anlamanız gerekir.

Aşağıdaki örnek, `MarshalingBehavior` `ThreadingModel` bir Windows çalışma zamanı sınıf kitaplığındaki çalışma zamanı sınıfına ve özniteliklerin nasıl uygulanacağını gösterir. Bir uygulama DLL 'i kullandığında ve `ref new` bir sınıf nesnesini etkinleştirmek için anahtar sözcüğünü kullandığında `MySTAClass` , nesne tek iş parçacıklı bir grupta etkinleştirilir ve sıralama desteklenmez.

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

- `ThreadingModel`Ve `MarshallingBehavior` öznitelikleri türetilmiş sınıfta tanımlı değil.

- `ThreadingModel` `MarshallingBehavior` Türetilmiş sınıftaki ve özniteliklerinin değerleri, taban sınıfındakilerle eşleşmiyor.

Üçüncü taraf Windows Çalışma Zamanı bileşeni için gereken iş parçacığı oluşturma ve sıralama bilgileri, bileşen için uygulama bildirimi kayıt bilgilerinde belirtilmiştir. Tüm Windows Çalışma Zamanı bileşenlerinizi çevik yapmanızı öneririz. Bu, istemci kodunun uygulamanızı uygulamadaki herhangi bir iş parçacığından çağırabilmesini sağlar ve bu çağrıların performansını artırır çünkü sıralama olmayan doğrudan çağrılar olur. Sınıfınızı bu şekilde yazarsa, istemci kodunun `Platform::Agile<T>` sınıfınızı tüketmek için kullanmak zorunda değildir.

## <a name="see-also"></a>Ayrıca bkz.

[ThreadingModel](/uwp/api/windows.foundation.metadata.threadingmodel)<br/>
[Sıralamada Allingbehavior](/uwp/api/windows.foundation.metadata.marshalingbehaviorattribute)
