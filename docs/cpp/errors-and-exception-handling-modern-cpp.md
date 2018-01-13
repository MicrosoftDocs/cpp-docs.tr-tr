---
title: "Hatalar ve özel durum işleme (Modern C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a6c111d0-24f9-4bbb-997d-3db4569761b7
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5b1ee1c7307f4e19db4ca0b7d03e218b0916538c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="errors-and-exception-handling-modern-c"></a>Hatalar ve Özel Durum İşleme (Modern C++)
Çoğu senaryoda, modern c++ rapor ve mantık hataları ve çalışma zamanı hataları işlemek için tercih edilen yöntem özel durumlar kullanmaktır. Yığın hatası algılarsa işlevi ve onu nasıl ele alınacağını bilmeniz bağlamı olan işlevi arasında birden fazla işlev çağrılarını içerebilir durumlarda özellikle geçerlidir. Özel durum çağrı yığını bilgileri geçirmek için hatalarını algılar kodu için resmi ve iyi tanımlanmış bir yol sağlar.  
  
 Program hataları genellikle iki kategoriye bölünmüş: bir "Ağ Hizmet kullanılamıyor" hatalar, örneğin programlama, "dizin aralık dışında" hata ve Programcı, denetimi ötesine Örneğin, çalışma zamanı hataları nedeniyle oluşan mantık hataları bir hata oluştu. C türü programlama ve COM, hata raporlama bir hata kodu ya da belirli bir işlev için durum kodunu temsil eden bir değer döndürerek veya çağıranın görmek için her işlev çağrısı sonra isteğe bağlı olarak alabilir genel bir değişkeni ayarlayarak yönetilir hataları olup olmadığını bildirildi. Örneğin, COM programlama hataları çağırana iletişim kurmak için HRESULT dönüş değerini kullanır ve Win32 API çağrı yığını tarafından bildirilen son hata almak için GetLastError işlevi vardır. Her iki durumda da, çağırana kodu tanımak ve uygun şekilde yanıtlamak için hazır. Arayan açıkça hata kodu işleyemez, program uyarmadan kilitlenme veya hatalı verilerle yürütün ve hatalı sonuçlar devam.  
  
 Özel durumlar modern C++'da aşağıdaki nedenlerle tercih edilen:  
  
-   Bir özel durum bir hata koşulu tanınması ve bu çağrıyı yapan kod zorlar. İşlenmeyen özel durumlar, program yürütme durdurun.  
  
-   Bir özel hatayı işleyebilir çağrı yığınında noktası atlar. Ara işlevleri yayılması özel durum izin verebilirsiniz. Diğer katmanlarıyla koordine gerekmez.  
  
-   Bir özel durum oluşturulduktan sonra özel durum yığını geriye doğru izleme mekanizması iyi tanımlanmış kurallarına göre kapsamındaki tüm nesnelerin bozar.  
  
-   Bir özel durum hatası algılarsa kodu ve hata işleme kodu arasında temiz bir ayrım sağlar.  
  
 Aşağıdaki Basitleştirilmiş örnekte atma ve C++'da özel durumları yakalama için gerekli sözdizimi gösterilmektedir.  
  
```cpp  
#include <stdexcept>  
#include <limits>  
#include <iostream>  
  
using namespace std;  
class MyClass  
{  
public:  
   void MyFunc(char c)  
   {  
      if(c < numeric_limits<char>::max())  
         throw invalid_argument("MyFunc argument too large.");  
      //...  
   }  
};  
  
int main()  
{  
   try  
   {  
      MyFunc(256); //cause an exception to throw  
   }  
  
   catch(invalid_argument& e)  
   {  
      cerr << e.what() << endl;  
      return -1;  
   }  
   //...  
   return 0;  
}  
  
```  
  
 C++ içinde özel durumları C# ve Java gibi dilleri de benzer. İçinde `try` bir özel durum ise bloğunu *durum* olacak *yakalanan* tarafından ilk ilişkili `catch` blok türü, özel durumun eşleşir. Diğer bir deyişle, gelen yürütme atlar `throw` ifadesine `catch` deyimi. Hiçbir kullanılabilir catch bloğu bulunursa, `std::terminate` çağrılır ve program çıkar. C++'da, herhangi bir tür durum; Ancak, doğrudan veya dolaylı olarak türeyen bir tür throw öneririz `std::exception`. Önceki örnekte, özel durum türü [invalid_argument](../standard-library/invalid-argument-class.md), standart Kitaplığı'nda tanımlanan [ \<stdexcept >](../standard-library/stdexcept.md) üstbilgi dosyası. C++ sağlamaz ve gerektirmeyen bir `finally` bloğu bir özel durum, tüm kaynakları serbest olduğundan emin olun. Kaynak edinme, akıllı işaretçiler kullanır, başlatma (RAII) deyim kaynak Temizleme için gerekli işlevselliği sağlar ' dir. Daha fazla bilgi için bkz: [nasıl yapılır: özel durum güvenliği tasarımı](../cpp/how-to-design-for-exception-safety.md). C++ yığın geriye doğru izleme mekanizması hakkında daha fazla bilgi için bkz: [özel durumlar ve yığını Unwinding](../cpp/exceptions-and-stack-unwinding-in-cpp.md).  
  
## <a name="basic-guidelines"></a>Temel yönergeleri  
 Sağlam hata işleme herhangi bir programlama dili zordur. Özel durumlar iyi hata işleme desteği çeşitli özellikler sunmasına karşın, bunlar tüm iş için bunu yapamazsınız. Özel durum mekanizması faydaları hayata geçirmek için özel durumlar kodunuzu tasarlarken göz önünde bulundurun.  
  
-   Hiçbir zaman gerçekleşeceğini hataları denetlemek için kullanım onaylar. Özel durumlar, örneğin, oluşabilecek hatalar için ortak işlevlerin parametreleri giriş doğrulama hatalarını denetlemek için kullanın. Daha fazla bilgi için başlıklı bölüme bakın **özel durumlar vs. Onaylar**.  
  
-   Hata işleme kodu hatası algılarsa kodundan tarafından bir veya daha fazla müdahalede bulunan işlev çağrılarını ayrılmış, özel durumlar kullanın. Hata işleme kodu sıkı şekilde bağlı-algıladığı kodu olduğunda hata kodları performans açısından kritik Döngülerde kullanmayı düşünün. 
  
-   Oluşturduğunda veya bir özel durum yayılması her işlev için üç özel durum garanti birini belirtin: güçlü garanti, temel garanti ya da nothrow (noexcept) garanti edilemez. Daha fazla bilgi için bkz: [nasıl yapılır: özel durum güvenliği tasarımı](../cpp/how-to-design-for-exception-safety.md).  
  
-   Değere göre özel durumlar oluşturma, başvuruya göre yakalayın. Ne işleyemiyor catch yok. 
  
-   C ++ 11'de kullanım dışı özel durum belirtimleri kullanmayın. Daha fazla bilgi için başlıklı bölüme bakın **özel durum belirtimleri ve noexcept**.  
  
-   Bunlar uyguladığınızda standart kitaplığı özel durum türleri kullanın. Özel durum türlerini türetmek [özel durum sınıfı](../standard-library/exception-class.md) hiyerarşisi.  
  
-   Yıkıcılar kaçış veya İşlevler bellek ayırmayı kaldırma özel durumlara izin verme.  
  
## <a name="exceptions-and-performance"></a>Özel durumları ve performans  
 Özel durum mekanizması hiçbir özel durum, bir çok az performans sahiptir. Bir özel durum, yığın geçişi, maliyet ve unwinding kabaca bir işlev çağrısı maliyetini karşılaştırılabilir. Ek veri yapılarını sonra çağrı yığını izlemek üzere gerekli bir `try` blok girilir ve ek yönergeler, bir özel durum yığını geriye doğru izleme için gereklidir. Bununla birlikte, çoğu senaryoda, maliyet performans ve bellek alanını önemli değildir. Büyük olasılıkla yalnızca çok bellek kısıtlı sistemlerinde önemli özel durumların performansı olumsuz etkileyebilir veya içinde performans açısından kritik burada bir hata oluştuğu düzenli olarak ve onu işlemek üzere kod rapor kodu sıkı şekilde bağlı döngüye girer. Herhangi bir durumda, özel durumların gerçek maliyet profil oluşturma ve ölçme bilmeniz mümkün değildir. Maliyet önemli olduğunda bu nadir durumlarda bile, onu artan doğruluğu, daha kolay bakım ve iyi tasarlanmış bir özel durum ilkesi tarafından sağlanan diğer avantajları karşı tartmanız.  
  
## <a name="exceptions-vs-assertions"></a>Özel durumlar onaylar karşılaştırması  
 Özel durumlar ve onaylar çalışma zamanı hataları bir programda algılama için iki farklı mekanizmalardır. Kullanım koşulları için hiçbir zaman tüm kodunuzun doğru ise doğru olması gereken geliştirme sırasında test etmek için onaylar. Bir özel durum hata kodu bir şey düzeltilmesi sahip olduğunu gösterir çünkü'ı kullanarak bu tür bir hata işlemedeki noktası yok ve çalışma zamanında kurtarılır program sahip bir koşulu temsil etmez. Assert deyim yürütmesi durur, böylece hata ayıklayıcı program durumda inceleyin; bir özel durum ilk uygun catch işleyicisinden yürütme devam eder. Çalışma zamanında kodunuzun doğru Örneğin, "dosya bulunamadı" olsa bile veya "yetersiz bellek." ortaya çıkabilecek hata koşullarını denetlemek için özel durumlar kullanma Kurtarma yalnızca bir günlük iletisine çıkarır ve programı sonlandırır olsa bile bu koşulları, kurtarmak istediğiniz. Her zaman özel durumları kullanarak genel işlev bağımsız değişkenleri denetleyin. İşlevinizi hatasız olsa bile, bir kullanıcı için geçebilir bağımsız değişken tam denetime sahip olmayabilir.  
  
## <a name="c-exceptions-versus-windows-seh-exceptions"></a>C++ özel durumlarını Windows SEH özel durumlar karşılaştırması  
 C ve C++ programlarında yapılandırılmış özel durum işleme (SEH) mekanizması Windows işletim sisteminde kullanabilirsiniz. SEH kullanır ancak bu SEH açıklanan kavramlar C++ özel durumlarını de benzer `__try`, `__except`, ve `__finally` yerine yapıları `try` ve `catch`. Visual C++'da C++ özel durumlarını SEH için uygulanır. Ancak, C++ kodu yazarken C++ özel durum sözdizimini kullanın.  
  
 SEH hakkında daha fazla bilgi için bkz: [yapılandırılmış özel durum işleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md).  
  
## <a name="exception-specifications-and-noexcept"></a>Özel durum belirtimleri ve noexcept  
 Özel durum belirtimleri C++'da bir işlev throw özel durumları belirtmek için bir yol tanıtıldı. Ancak, özel durum belirtimleri uygulamada sorunlu oluyor uygulamasına yol açıyordu ve C ++ 11 taslak standart dışı bırakılmıştır. Özel durum belirtimleri dışında kullanmamanızı öneririz `throw()`, işlevi kaçınmak hiçbir özel durum izin verdiğini gösterir. Özel durum belirtimleri türü kullanmanız gerekiyorsa `throw(` *türü*`)`, Visual C++ belirli şekillerde standardı departs unutmayın. Daha fazla bilgi için bkz: [özel durum belirtimleri (throw)](../cpp/exception-specifications-throw-cpp.md). `noexcept` Tercih edilen alternatif olarak, C ++ 11 belirleyici sunulmuştur `throw()`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: özel durumlu ve özel durumlu olmayan kod arasındaki arabirim](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)   
 [C++ için yeniden Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
