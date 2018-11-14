---
title: Hatalar ve Özel Durum İşleme (Modern C++)
ms.date: 09/17/2018
ms.topic: conceptual
ms.assetid: a6c111d0-24f9-4bbb-997d-3db4569761b7
ms.openlocfilehash: d6192ab800667ceb35bf2e18dcbdc0be95ec70f5
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523294"
---
# <a name="errors-and-exception-handling-modern-c"></a>Hatalar ve Özel Durum İşleme (Modern C++)

Çoğu senaryoda, modern C++'ta rapor ve mantık hatalarını ve çalışma zamanı hataları işlemek için tercih edilen yol özel durumları kullanmaktır. Yığın hatayı algılayan işlevi ve sahip nasıl işleyeceğini bilen işlev arasında birden fazla işlev çağrısı içerdiğinde bu özellikle doğrudur. Özel durumlar, bilgileri çağrı yığınına aktarmak üzere hataları algılayan kod için biçimsel ve iyi tanımlanmış bir yol sağlar.

Program hataları genellikle iki kategoriye ayrılmıştır: hatalar, örneğin programlama, "dizin aralık dışında" hata ve programlayıcının kontrolü dışında dışında Örneğin, çalışma zamanı hataları nedeniyle bir "Ağ Hizmeti kullanılamıyor" oluşan mantık hataları bir hata oluştu. C stili programlamada ve com'da hata raporlama bir hata kodu veya belirli bir işlev için durum kodu temsil eden bir değer döndürerek veya çağıranın görmek için her işlev çağrısından sonra isteğe bağlı olarak alabileceği genel bir değişken ayarlanarak yönetilir hataları olup olmadığını bildirildi. Örneğin, COM programlama, hataları arayana iletişim kurmak için HRESULT dönüş değerini kullanır ve Win32 API çağrısı yığını tarafından bildirilen son hatayı alması için GetLastError işlevi vardır. Her iki durumda, bu da kodun tanınması ve uygun şekilde yanıtlanması arayana aittir. Arayan açıkça hata kodunu işlemezse program uyarı vermeden kilitlenebilir veya hatalı sonuçlar verir ve hatalı verilerle yürütülmeye devam.

Özel durumlar, modern C++'da aşağıdaki nedenlerden dolayı tercih edilir:

- Bir özel durum, çağırma kodunun bir hata durumunu tanıması ve işlemesi için zorlar. İşlenmeyen özel durumlar programın yürütülmesini durdurur.

- Bir özel durum çağrı yığınında hatayı işleyebilen noktaya atlar. Ara işlevler özel durumun yayılmasını izin verebilirsiniz. Diğer katmanlarla koordine gerekmez.

- Özel durum yığın geriye doğru mekanizması bir özel durum oluşmasından sonra iyi tanımlanmış kurallara göre kapsam içindeki tüm nesneleri yok eder.

- Bir özel durum, hatayı algılayan kod ile hatayı işleyen kod arasında NET bir ayrım sağlar.

Aşağıdaki Basitleştirilmiş örnekte oluşturmak ve C++ özel durumları yakalamak için gerekli sözdizimi gösterilir.

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

C++ içindeki özel durumlar bu C# ve Java gibi dillerdeki benzer. İçinde **deneyin** bir özel durum bloğunda *durum* olacaktır *yakalandı* ilk ilişkili **catch** olan türüyle eşleşen blok özel durum. Yürütme başka bir deyişle, atlar **throw** ifadesine **catch** deyimi. Kullanılabilir catch bloğu bulunduysa `std::terminate` çağrılır ve programdan çıkılır. C++'da, herhangi bir tür oluşturulabilir; Ancak, doğrudan veya dolaylı olarak türetir tür throw öneririz `std::exception`. Önceki örnekte, özel durum türü [invalid_argument](../standard-library/invalid-argument-class.md), standart kitaplıkta tanımlanan [ \<stdexcept >](../standard-library/stdexcept.md) üst bilgi dosyası. C++ sağlamaz ve gerektirmeyen bir **son** bir özel durum oluşturulursa tüm kaynakların serbest bırakıldığından emin olmak için blok. Kaynak alımı başlatma (RAII) deyimidir, akıllı işaretçiler kullanan kaynak Temizleme için gereken işlevselliği sağlar ' dir. Daha fazla bilgi için [nasıl yapılır: özel durum güvenliği tasarımı](../cpp/how-to-design-for-exception-safety.md). C++ yığın geriye doğru izleme mekanizması hakkında daha fazla bilgi için bkz: [özel durumlar ve yığını geriye doğru izleme](../cpp/exceptions-and-stack-unwinding-in-cpp.md).

## <a name="basic-guidelines"></a>Temel yönergeler

Herhangi bir programlama dilinde güçlü hata işleme zordur. Özel durumlar hata işlemeyi iyi destekleyen çeşitli özellikler sağlasa da, bunlar işin tümünü sizin yerinize gerçekleştiremez. Özel durum düzeneğinin avantajlardan faydalanmak için kodunuzun tasarlarken özel durumları göz önünde bulundurun.

- Gereken hataları denetlemek için kullanım onaylar. Genel işlev parametrelerinin giriş doğrulamalarındaki hatalar, örneğin, oluşabilecek hataları denetlemek için özel durumları kullanın. Daha fazla bilgi için bkz. bölümüne **özel durumları vs. Onaylamalar**.

- Hatayı işleyen kodun hatayı algılayan koddan bir veya daha fazla işlev çağrısıyla ayrılabileceği durumlarda özel durumları kullanın. Hatayı işleyen kod, algıladığı koda sıkıca bağlı olduğunda hata kodları performans açısından kritik döngüler yerine kullanıp kullanmayacağınızı düşünün.

- Throw veya bir özel durum yayan her işlev için üç özel durum garantisinden birini sağlayın: güçlü garanti, temel garanti veya nothrow (noexcept) garantisi. Daha fazla bilgi için [nasıl yapılır: özel durum güvenliği tasarımı](../cpp/how-to-design-for-exception-safety.md).

- Özel durumları değere göre oluşturun, başvuruya göre yakalayın. İşleyemeyeceğiniz hiçbir öğeyi yakalamayın.

- C ++ 11'de kullanım dışı özel durum belirtimlerini kullanmayın. Daha fazla bilgi için bkz. bölümüne **özel durum belirtimleri ve noexcept**.

- Geçerli olduğu durumlarda standart kitaplık özel durum türlerini kullanın. Özel durum'türleri türetin [özel durum sınıfı](../standard-library/exception-class.md) hiyerarşisi.

- Özel durumlar edicilerden veya bellek-ayırma kaldırma işlevlerinden kurtulmasına izin vermeyin.

## <a name="exceptions-and-performance"></a>Özel durumlar ve performans

Özel durum mekanizması çok az performans hiçbir özel durum oluşturulursa maliyetine sahiptir. Bir özel durum oluşturulursa, yığın geçişi maliyet ve geriye doğru izleme maliyeti işlev çağrısı için kabaca karşılaştırılabilir. Ek veri yapıları sonra çağırma yığınını izlemek için gerekli bir **deneyin** bloğu girildikten ve ek yönergeler, bir özel durum oluşturulursa yığını geriye doğru izleme için gereklidir. Ancak, çoğu senaryoda performans ve bellek Ayak izi maliyeti önemli değildir. Özel durumların performans üzerindeki olumsuz etkisi, yalnızca belleği çok kısıtlı sistemlerde önemli hale gelmesi muhtemeldir veya içinde performans açısından kritik burada bir hata, düzenli aralıklarla gerçekleşecek şekilde olasıdır ve bunu işlemek üzere kod rapor koda sıkı şekilde bağlı döngü oluşturur. Her durumda profil oluşturma veya ölçme yapılmadan özel durumların gerçek maliyetini bilmek olanaksızdır. Maliyet önemli olduğunda taşıdığı nadir durumlarda bile, bunu artırılmış doğruluk, daha kolay sürdürülebilirlik ve iyi tasarlanmış bir özel durum ilkesi tarafından sağlanan diğer avantajları karşı Tart.

## <a name="exceptions-vs-assertions"></a>Özel durumlar ile onaylar

Özel durumlar ve onaylama işlemleri bir programda çalışma zamanı hataları algılamak için iki ayrı mekanizmadır. Kullanım koşulları için hiçbir zaman tüm kodunuz doğruysa true olması gereken geliştirme sırasında test etmek için onaylar. Özel durum hatası kodu bir şey düzeltilmesi gereken olduğunu belirttiğinden'ı kullanarak bu tür bir hataya işlemedeki noktası yok ve program çalışma zamanında kurtarılır sahip bir koşulu temsil etmez. Hata ayıklayıcıdaki program durumunu denetleyebilmeniz için deyimdeki yürütmeyi durdurur; bir özel durum yürütmeyi ilk uygun catch işleyicisinden devam eder. Çalışma zamanında bile kodunuzun doğru Örneğin, "dosya bulunamadı" veya "yetersiz bellek." ortaya çıkabilecek hata koşullarını denetlemek için özel durumları kullanın Kurtarma yalnızca bir günlük için ileti sunsa ve programı sonlandırsa bile bu koşullar, kurtarılır isteyebilirsiniz. Her zaman özel durumları kullanarak genel işlev bağımsız değişkenleri denetleyin. İşleviniz hatadan arınmış olsa bile, bir kullanıcının buna geçirebileceği bağımsız değişkenler üzerinde tam denetime sahip olmayabilir.

## <a name="c-exceptions-versus-windows-seh-exceptions"></a>C++ özel durumlarına karşı Windows SEH özel durumları

Hem C ve C++ programları, yapılandırılmış özel durum işleme (SEH) mekanizmasını Windows işletim sisteminde kullanabilirsiniz. SEH kullanması hariç, SEH içindeki kavramlar C++ özel durumlarını, de benzer **__try**, **__except**, ve **__finally** yerine yapıları **deneyin** ve **catch**. Visual C++'da, C++ özel durumları SEH için uygulanır. Bununla birlikte, C++ kodu yazarken C++ özel durum söz dizimini kullanın.

SEH hakkında daha fazla bilgi için bkz: [yapılandırılmış özel durum işleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md).

## <a name="exception-specifications-and-noexcept"></a>Özel durum belirtimleri ve noexcept

Özel durum belirtimleri bir işlevin oluşturulabileceği özel durumları belirtme yöntemi olarak C++ ile sunulur. Ancak, özel durum belirtimleri uygulamada sorun kanıtlandı ve C ++ 11 taslak standardı kullanım dışı bırakılmıştır. Özel durum belirtimleri dışında kullanmamanızı öneririz `throw()`, işlev kaçış özel durum yok izin verdiğini gösterir. Türündeki özel durum belirtimlerini kullanmanız gerekirse `throw(` *türü*`)`, Visual C++ standardı belirli yollarla departs unutmayın. Daha fazla bilgi için [özel durum belirtimleri (throw)](../cpp/exception-specifications-throw-cpp.md). `noexcept` Tanımlayıcısı için tercih edilen alternatif olarak C ++ 11'de sunulmuştur `throw()`.

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Özel Durumlu Kod ve Özel Durumlu Olmayan Kod Arasında Arabirim](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)<br/>
[C++ tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)