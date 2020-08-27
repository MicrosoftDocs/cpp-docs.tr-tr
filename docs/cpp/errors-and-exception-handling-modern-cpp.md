---
title: Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları
description: Modern C++ hata kodları üzerinde olağanüstü programlama stillerini nasıl destekler.
ms.date: 08/24/2020
ms.topic: conceptual
ms.assetid: a6c111d0-24f9-4bbb-997d-3db4569761b7
ms.openlocfilehash: b402c93ea5af3cc7dab418b6dea58446ae300c67
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898377"
---
# <a name="modern-c-best-practices-for-exceptions-and-error-handling"></a>Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları

Modern C++ ' da çoğu senaryoda, hem mantık hatalarını hem de çalışma zamanı hatalarını raporlamak ve işlemek için tercih edilen yöntem, özel durumları kullanmaktır. Yığın, hatayı algılayan işlev ve hatayı işlemek için bağlam olan işlev arasında birkaç işlev çağrısı içerdiğinde özellikle doğrudur. Özel durumlar, bilgileri çağrı yığınına iletmek için hataları algılayan kod için biçimsel ve iyi tanımlanmış bir yol sağlar.

## <a name="use-exceptions-for-exceptional-code"></a>Olağanüstü kod için özel durumlar kullanın

Program hataları genellikle iki kategoriye ayrılmıştır: hata programlama hatasından kaynaklanan mantık hataları, örneğin, "Dizin aralık dışında" hatası. Ve, örneğin, "ağ hizmeti kullanılamıyor" hatası gibi programcı denetiminin ötesinde çalışma zamanı hataları. C stili programlamada ve COM 'da, hata raporlama bir hata kodunu veya belirli bir işlev için durum kodunu temsil eden bir değer döndürerek ya da hatanın raporlanıp raporlanmadığını görmek için her işlev çağrısından sonra arayan tarafından isteğe bağlı olarak alabileceği genel bir değişken ayarlanarak yönetilir. Örneğin, COM programlama, hataları çağırana iletmek için HRESULT dönüş değeri kullanır. Win32 API, `GetLastError` çağrı yığını tarafından raporlanan son hatayı alma işlevine sahiptir. Bu iki durumda da, kodu tanımak ve buna uygun şekilde yanıt vermek için çağrı yapana kadar olur. Çağıran hata kodunu açıkça işlemezse, program uyarı vermeden kilitlenebilir. Ya da, hatalı verileri kullanarak yürütmeye devam edebilir ve hatalı sonuçlar üretebilir.

Özel durumlar, modern C++ ' da aşağıdaki nedenlerle tercih edilir:

- Bir özel durum kodu çağırarak hata koşulunu tanımasını ve işlemesini zorlar. İşlenmeyen özel durumlar program yürütmeyi durdurur.

- Bir özel durum, çağrı yığınında hatayı işleyebilen noktaya atlar. Ara işlevler özel durumun yaymasına izin verebilir. Diğer katmanlarla koordine etmek zorunda kalmaz.

- Özel durum yığın geri sarma mekanizması, iyi tanımlanmış kurallara göre bir özel durum oluşturulduktan sonra kapsamdaki tüm nesneleri yok eder.

- Bir özel durum, hatayı algılayan kod ve hatayı işleyen kod arasında temiz bir ayrım sunar.

Aşağıdaki basitleştirilmiş örnek, C++ ' da özel durumlar oluşturmak ve yakalamak için gerekli sözdizimini gösterir.

```cpp
#include <stdexcept>
#include <limits>
#include <iostream>

using namespace std;

void MyFunc(int c)
{
    if (c > numeric_limits< char> ::max())
        throw invalid_argument("MyFunc argument too large.");
    //...
}

int main()
{
    try
    {
        MyFunc(256); //cause an exception to throw
    }

    catch (invalid_argument& e)
    {
        cerr << e.what() << endl;
        return -1;
    }
    //...
    return 0;
}
```

C++ içindeki özel durumlar C# ve Java gibi dillerde benzer. **`try`** Bloğunda, bir özel durum *oluşturulursa* , türü özel durumla eşleşen ilk ilişkili blok tarafından *yakalanacaktır* **`catch`** . Diğer bir deyişle, yürütme **`throw`** deyimden **`catch`** deyime atlar. Kullanılabilir bir catch bloğu bulunmazsa, `std::terminate` çağrılır ve program çıkar. C++ ' da herhangi bir tür oluşturulabilir; Ancak doğrudan veya dolaylı olarak kaynağından türetilmiş bir tür oluşturmanız önerilir `std::exception` . Önceki örnekte, özel durum türü, [`invalid_argument`](../standard-library/invalid-argument-class.md) üstbilgi dosyasındaki standart kitaplıkta tanımlanmıştır [`<stdexcept>`](../standard-library/stdexcept.md) . **`finally`** Bir özel durum oluşursa, C++ tüm kaynakların serbest olduğundan emin olmak için bir blok sağlamaz veya gerektirmez. Kaynak alımı, akıllı işaretçiler kullanan başlatma (Çıı) deyimidir, kaynak Temizleme için gerekli işlevselliği sağlar. Daha fazla bilgi için bkz. [nasıl yapılır: özel durum güvenliği tasarımı](how-to-design-for-exception-safety.md). C++ yığın geri sarma mekanizması hakkında daha fazla bilgi için bkz. [özel durumlar ve yığın geri sarma](exceptions-and-stack-unwinding-in-cpp.md).

## <a name="basic-guidelines"></a>Temel yönergeler

Sağlam hata işleme, herhangi bir programlama dilinde zorlayıcı bir işlem olabilir. Özel durumlar iyi hata işlemeyi destekleyen çeşitli özellikler sunmakla birlikte, tüm işleri sizin için yapamazlar. Özel durum mekanizmalarının avantajlarından yararlanmak için, kodunuzu tasarlarken özel durumları göz önünde bulundurun.

- Hiçbir koşulda gerçekleşmeyecek hataları denetlemek için onayları kullanın. Olabilecek hataları denetlemek için özel durumları kullanın, örneğin, genel işlevlerin parametrelerinde giriş doğrulamasında hatalar. Daha fazla bilgi için [özel durumlar ve onaylama](#exceptions_versus_assertions) bölümlerine bakın.

- Hatayı işleyen kod, bir veya daha fazla araya giren işlev çağrısı tarafından hatayı algılayan koddan ayrıldığı zaman özel durumlar kullanın. Performans açısından kritik Döngülerde hata kodları kullanıp kullanmayacağınızı göz önünde bulundurun. hatayı işleyen kod, onu algılayan kodla sıkı bir şekilde bağlanmış olduğunda.

- Özel durum oluşturabilecek veya yaymaya yönelik her işlev için, üç özel durum garantisini belirtin: güçlü garanti, temel garanti veya nothrow (noexcept) garantisi. Daha fazla bilgi için bkz. [nasıl yapılır: özel durum güvenliği tasarımı](how-to-design-for-exception-safety.md).

- Değere göre özel durumlar throw, bunları başvuruya göre yakala. İşleyememenizi yakalayamıyorum.

- C++ 11 ' de kullanım dışı olan özel durum belirtimlerini kullanmayın. Daha fazla bilgi için bkz. [özel durum belirtimleri `noexcept` ve](#exception_specifications_and_noexcept) bölümü.

- Uygulandıklarında standart kitaplık özel durum türlerini kullanın. [ `exception` Sınıf](../standard-library/exception-class.md) hiyerarşisinden özel özel durum türleri türet.

- Özel durumların yok edicilerin veya bellek ayırmayı kaldırma işlevlerinin çıkmasına izin verme.

## <a name="exceptions-and-performance"></a>Özel durumlar ve performans

Özel durum belirtilmemişse, özel durum mekanizmasının en düşük performans maliyeti vardır. Bir özel durum oluşursa, yığın geçişi ve geri sarma maliyeti, bir işlev çağrısının maliyetiyle kabaca karşılaştırılabilir. Bir blok girildikten sonra çağrı yığınını izlemek için ek veri yapıları gerekir **`try`** ve bir özel durum oluşturulursa yığını geriye doğru geri yüklemek için ek yönergeler gereklidir. Ancak çoğu senaryoda performans ve bellek kaplama maliyeti önemli değildir. Özel durumların olumsuz etkisinin performansı büyük olasılıkla yalnızca bellek kısıtlı sistemlerde önemli olabilir. Ya da bir hatanın düzenli olarak oluşma olasılığı olan performans açısından kritik Döngülerde ve bunu işlemek için kod ile onu raporlayan kod arasında sıkı bir bağlantının vardır. Herhangi bir durumda, profil oluşturma ve ölçüm olmadan özel durumların gerçek maliyetini haberdar etmek olanaksızdır. Maliyetin önemli olduğu nadir durumlarda bile, daha yüksek doğruluk, daha kolay bakım ve iyi tasarlanmış bir özel durum ilkesi tarafından sağlanmış diğer avantajlara karşı bu şekilde ağırlık uygulayabilirsiniz.

## <a name="exceptions-versus-assertions"></a><a name="exceptions_versus_assertions"></a> Özel durumlar ve Onaylamalar

Özel durumlar ve Onaylamalar, bir programdaki çalışma zamanı hatalarını saptamak için iki ayrı mekanizmalarda bulunur. `assert`Tüm kodunuzun doğru olması durumunda, geliştirme sırasında asla doğru olmaması gereken koşulları test etmek için deyimlerini kullanın. Hata, koddaki bir şeyin düzeltildiğini gösterdiği için bir özel durum kullanılarak bu tür bir hata işlenmediğinde bir nokta yoktur. Çalışma zamanında programın kurtarmak için gereken bir koşulu temsil etmez. , `assert` Hata ayıklayıcıda program durumunu incelemenize olanak sağlamak üzere deyimden yürütmeyi durduruyor. Bir özel durum, yürütmeyi ilk uygun catch işleyicisinden devam ettirir. Kodunuz doğru olsa bile çalışma zamanında oluşabilecek hata koşullarını denetlemek için özel durumları kullanın, örneğin, "dosya bulunamadı" veya "bellek yetersiz". Kurtarma yalnızca bir günlüğe ileti çıkarsa ve programı sona erse bile, özel durumlar bu koşulları işleyebilir. Özel durumları kullanarak her zaman ortak işlevlere bağımsız değişkenleri denetleyin. İşleviniz hatasız olsa bile, bir kullanıcının kendisine geçebileceğini bağımsız değişkenler üzerinde tam denetim sahibi olmayabilirsiniz.

## <a name="c-exceptions-versus-windows-seh-exceptions"></a>C++ özel durumları ve Windows SEH özel durumları karşılaştırması

C ve C++ programları, Windows işletim sisteminde yapılandırılmış özel durum işleme (SEH) mekanizmasını kullanabilir. SEH içindeki kavramlar C++ özel durumlarına benzer, ancak SEH **`__try`** , **`__except`** **`__finally`** ve yerine yapılarını kullanır **`try`** **`catch`** . Microsoft C++ derleyicisinde (MSVC), C++ özel durumları SEH için uygulanır. Ancak, C++ kodu yazdığınızda C++ özel durum söz dizimini kullanın.

SEH hakkında daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme (C/C++)](structured-exception-handling-c-cpp.md).

## <a name="exception-specifications-and-noexcept"></a><a name="exception_specifications_and_noexcept"></a> Özel durum belirtimleri ve `noexcept`

Özel durum belirtimleri, C++ ' da bir işlevin oluşturabilecek özel durumları belirtmenin bir yolu olarak sunulmuştur. Ancak, özel durum belirtimleri uygulamada sorunlu olması ve C++ 11 taslak standardında kullanım dışı bırakılmıştır. **`throw`** `throw()` İşlevin kaçış dışı bir özel durum olmayacağını belirten, hariç özel durum belirtimleri kullanmamalarını öneririz. Kullanım dışı bırakılan formun özel durum belirtimlerini kullanmanız gerekiyorsa `throw( type-name )` MSVC desteği sınırlıdır. Daha fazla bilgi için bkz. [özel durum belirtimleri (throw)](exception-specifications-throw-cpp.md). **`noexcept`** Belirleyici, c++ 11 ' de tercih edilen alternatifi olarak tanıtılmıştır `throw()` .

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: olağanüstü ve olağanüstü olmayan kod arasında arabirim](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)<br/>
[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md)
