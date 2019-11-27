---
title: Özel C++ durumlar ve hata işleme için modern en iyi uygulamalar
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: a6c111d0-24f9-4bbb-997d-3db4569761b7
ms.openlocfilehash: 85a8bf0f64681387cbee63f273fda5ce93ab7ad5
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245863"
---
# <a name="modern-c-best-practices-for-exceptions-and-error-handling"></a>Özel C++ durumlar ve hata işleme için modern en iyi uygulamalar

Modern C++' de çoğu senaryoda, hem mantık hatalarını hem de çalışma zamanı hatalarını raporlamak ve işlemek için tercih edilen yöntem, özel durumları kullanmaktır. Bu, yığın, hatayı algılayan işlev ve bu işlemi nasıl ele alınacağını öğrenmek için bağlam olan işlevi arasında birkaç işlev çağrısı içerebileceği zaman özellikle doğrudur. Özel durumlar, bilgileri çağrı yığınına iletmek için hataları algılayan kod için biçimsel ve iyi tanımlanmış bir yol sağlar.

Program hataları genellikle iki kategoriye ayrılmıştır: Örneğin, bir "Dizin aralık dışında" hatası ve programlamanın denetimini aşan çalışma zamanı hataları, örneğin "ağ hizmeti kullanılamıyor" hatayla. C stili programlamada ve COM 'da, hata raporlama bir hata kodunu veya belirli bir işlev için durum kodunu temsil eden bir değer döndürerek ya da çağıranın her işlev çağrısından sonra isteğe bağlı olarak alabileceği genel bir değişken ayarlanarak yönetilir. hataların raporlanıp bildirilmediğini belirtir. Örneğin, COM programlama, hataları çağırana iletmek için HRESULT dönüş değerini kullanır ve Win32 API, çağrı yığını tarafından raporlanan son hatayı almak için GetLastError işlevine sahiptir. Bu iki durumda da, kodu tanımak ve buna uygun şekilde yanıt vermek için çağrı yapana kadar olur. Çağıran, hata kodunu açıkça işlemezse, program uyarı olmadan kilitlenebilir veya hatalı verilerle yürütmeye devam edebilir ve hatalı sonuçlar üretebilir.

Aşağıdaki nedenlerle özel durumlar modern C++ olarak tercih edilir:

- Bir özel durum kodu çağırarak hata koşulunu tanımasını ve işlemesini zorlar. İşlenmeyen özel durumlar program yürütmeyi durdurur.

- Bir özel durum, çağrı yığınında hatayı işleyebilen noktaya atlar. Ara işlevler özel durumun yaymasına izin verebilir. Diğer katmanlarla koordine etmek zorunda değildir.

- Özel durum yığın geri sarma mekanizması, bir özel durum oluşturulduktan sonra iyi tanımlanmış kurallara göre kapsamdaki tüm nesneleri yok eder.

- Bir özel durum, hatayı algılayan kod ve hatayı işleyen kod arasında temiz bir ayrım sunar.

Aşağıdaki basitleştirilmiş örnek, içindeki C++özel durumları oluşturmak ve yakalamak için gerekli sözdizimini gösterir.

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

C++ Ve Java gibi dillerdeki özel C# durumlar. **TRY** bloğunda, bir özel durum *oluşturulursa* , türü özel durum ile eşleşen ilk ilişkili **catch** bloğu tarafından *yakalanacaktır* . Diğer bir deyişle, yürütme **throw** deyimden **catch** ifadesine atlar. Kullanılabilir bir catch bloğu bulunmazsa, `std::terminate` çağrılır ve program çıkar. ' C++De, herhangi bir tür oluşturulabilir; Ancak, `std::exception`doğrudan veya dolaylı olarak türetilen bir tür oluşturmanız önerilir. Önceki örnekte, [invalid_argument](../standard-library/invalid-argument-class.md)özel durum türü, standart kitaplıkta [\<stdexcept >](../standard-library/stdexcept.md) üst bilgi dosyasında tanımlanmıştır. C++, bir özel durum oluşturulursa tüm kaynakların serbest olduğundan emin olmak için bir **finally** bloğu sağlamaz ve gerektirmez. Kaynak alımı, akıllı işaretçiler kullanan başlatma (Çıı) deyimidir, kaynak Temizleme için gerekli işlevselliği sağlar. Daha fazla bilgi için bkz. [nasıl yapılır: özel durum güvenliği tasarımı](how-to-design-for-exception-safety.md). C++ Yığın geri sarma mekanizması hakkında daha fazla bilgi için bkz. [özel durumlar ve yığın geri sarma](exceptions-and-stack-unwinding-in-cpp.md).

## <a name="basic-guidelines"></a>Temel yönergeler

Sağlam hata işleme, herhangi bir programlama dilinde zorlayıcı bir işlem olabilir. Özel durumlar iyi hata işlemeyi destekleyen çeşitli özellikler sunmakla birlikte, tüm işleri sizin için yapamazlar. Özel durum mekanizmalarının avantajlarından yararlanmak için, kodunuzu tasarlarken özel durumları göz önünde bulundurun.

- Hiçbir koşulda gerçekleşmeyecek hataları denetlemek için onayları kullanın. Olabilecek hataları denetlemek için özel durumları kullanın, örneğin, genel işlevlerin parametrelerinde giriş doğrulamasında hatalar. Daha fazla bilgi için **özel durumlar ve Onaylamalar**başlıklı bölüme bakın.

- Hatayı işleyen kod, bir veya daha fazla araya giren işlev çağrısı tarafından hatayı algılayan koddan ayrıldıysa özel durumları kullanın. Hatayı işleyen kod, onu algılayan kodla sıkı bir şekilde bağlanmış olduğunda, performans açısından kritik Döngülerde hata kodları kullanıp kullanmayacağınızı düşünün.

- Özel durum oluşturabilecek veya yaymaya yönelik her işlev için, üç özel durum garantisini belirtin: güçlü garanti, temel garanti veya nothrow (noexcept) garantisi. Daha fazla bilgi için bkz. [nasıl yapılır: özel durum güvenliği tasarımı](how-to-design-for-exception-safety.md).

- Değere göre özel durumlar throw, bunları başvuruya göre yakala. İşleyememenizi yakalayamıyorum.

- C++ 11 ' de kullanım dışı olan özel durum belirtimlerini kullanmayın. Daha fazla bilgi için **özel durum belirtimleri ve noexcept**başlıklı bölüme bakın.

- Uygulandıklarında standart kitaplık özel durum türlerini kullanın. Özel durum türleri özel durum [sınıfı](../standard-library/exception-class.md) hiyerarşisinden türetirsiniz.

- Özel durumların yok edicilerin veya bellek ayırmayı kaldırma işlevlerinin çıkmasına izin verme.

## <a name="exceptions-and-performance"></a>Özel durumlar ve performans

Özel durum belirtilmemişse, özel durum mekanizması çok az performans maliyetine sahiptir. Bir özel durum oluşursa, yığın geçişi ve geri sarma maliyeti, bir işlev çağrısının maliyetiyle kabaca karşılaştırılabilir. Bir **TRY** bloğu girildikten sonra çağrı yığınını izlemek için ek veri yapıları gerekir ve bir özel durum oluşturulursa yığını geriye doğru geri yüklemek için ek yönergeler gereklidir. Bununla birlikte, Çoğu senaryoda performans ve bellek parmak izi maliyeti önemli değildir. Özel durumların olumsuz etkisi, yalnızca çok fazla bellekle sınırlı sistemde veya bir hatanın düzenli olarak gerçekleşmesi ve işleme kodunun onu raporlayan kodla sıkı bir şekilde bağlanmış olması durumunda önemli bir öneme sahip olabilir. Herhangi bir durumda, profil oluşturma ve ölçüm olmadan özel durumların gerçek maliyetini haberdar etmek olanaksızdır. Maliyetin önemli olduğu nadir durumlarda bile, daha yüksek doğruluk, daha kolay bakım ve iyi tasarlanmış bir özel durum ilkesi tarafından sağlanmış diğer avantajlara karşı bu şekilde ağırlık uygulayabilirsiniz.

## <a name="exceptions-vs-assertions"></a>Özel durumlar ve Onaylamalar karşılaştırması

Özel durumlar ve Onaylamalar, bir programdaki çalışma zamanı hatalarını saptamak için iki ayrı mekanizmalarda bulunur. Tüm kodunuzun doğru olması durumunda, geliştirme sırasında asla doğru olmaması gereken koşulları test etmek için onayları kullanın. Hata, koddaki bir şeyin düzeltildiğini gösterdiği ve programın çalışma zamanında kurtarıldığı bir koşulu temsil etmediği için bir özel durum kullanarak bu tür bir hata ele alınmaz. Bir onaylama, hata ayıklayıcıda program durumunu inceleyebilmeniz için deyimdeki yürütmeyi sonlandırır; bir özel durum, yürütmeyi ilk uygun catch işleyicisinden devam ettirir. Kodunuz doğru olsa bile çalışma zamanında oluşabilecek hata koşullarını denetlemek için özel durumları kullanın, örneğin, "dosya bulunamadı" veya "bellek yetersiz". Kurtarma yalnızca bir günlüğe ileti çıkarsa ve programı sona erse bile bu koşullardan kurtarmak isteyebilirsiniz. Özel durumları kullanarak her zaman ortak işlevlere bağımsız değişkenleri denetleyin. İşleviniz hatasız olsa bile, bir kullanıcının kendisine geçebileceğini bağımsız değişkenler üzerinde tam denetim sahibi olmayabilirsiniz.

## <a name="c-exceptions-versus-windows-seh-exceptions"></a>C++özel durumlar ve Windows SEH özel durumları karşılaştırması

C ve C++ programlar, Windows işletim sisteminde yapılandırılmış özel durum Işleme (SEH) mekanizmasını kullanabilir. SEH C++ içindeki kavramlar, özel durumlarla benzer, ancak seh, **TRY** ve **catch**yerine **__try**, **__except**ve **__finally** yapılarını kullanır. Microsoft C++ derleyicisinde (MSVC), C++ özel durumlar SEH için uygulanır. Ancak, kod yazdığınızda C++ C++ özel durum sözdizimini kullanın.

SEH hakkında daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme (C++C/)](structured-exception-handling-c-cpp.md).

## <a name="exception-specifications-and-noexcept"></a>Özel durum belirtimleri ve noexcept

Özel durum belirtimleri, bir C++ işlevin oluşturabilecek özel durumları belirtmenin bir yolu olarak sunulmuştur. Ancak, özel durum belirtimleri uygulamada sorunlu olması ve C++ 11 taslak standardında kullanım dışı bırakılmıştır. İşlevin kaçış için hiçbir özel durum olmayacağını belirten `throw()`dışında özel durum belirtimleri kullanmamız önerilir. `throw(`*tür*`)`için özel durum belirtimleri kullanmanız GEREKIYORSA, MSVC 'in bazı yollarla standart parçalar halinde olduğunu unutmayın. Daha fazla bilgi için bkz. [özel durum belirtimleri (throw)](exception-specifications-throw-cpp.md). `noexcept` Belirleyicisi, `throw()`için tercih edilen alternatif olarak C++ 11 ' de kullanıma sunulmuştur.

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Özel Durumlu Kod ve Özel Durumlu Olmayan Kod Arasında Arabirim](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
