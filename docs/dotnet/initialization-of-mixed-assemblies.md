---
title: "Karışık derlemeleri başlatma | Microsoft Docs"
ms.custom: 
ms.date: 03/09/2018
ms.technology:
- cpp-windows
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- mixed assemblies [C++], loader lock
- loader lock [C++]
- initializing mixed assemblies
- deadlocks [C++]
- .cctor [C++]
- custom locales [C++]
- mixed assemblies [C++], initilizing
ms.assetid: bfab7d9e-f323-4404-bcb8-712b15f831eb
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c4d569987c20a962b0cecf22cd6888b22c920fb5
ms.sourcegitcommit: eb246547c7c9adc7d7ac4083ef09bf6e54dec914
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="initialization-of-mixed-assemblies"></a>Karışık Derlemeleri Başlatma

Windows geliştiricileri her zaman olmalıdır yükleyici kilidi dikkatli sırasında kodu çalıştırırken `DllMain`. Ancak, C + ile ilgilenirken oyuna gelen bazı hususlar vardır +/ clr karma mod derlemeler.

İçindeki kod [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583) CLR erişemezler gerekir. Bunun anlamı `DllMain` yönetilen işlevler hiçbir çağrı yapmak, doğrudan veya dolaylı olarak; hiç bir yönetilen kod bildirilen veya uygulanan `DllMain`; ve herhangi bir atık toplama veya otomatik kitaplık yükleme içinde gerçekleşeceğini `DllMain` .
  
## <a name="causes-of-loader-lock"></a>Yükleyici kilidi nedenleri

.NET platformu başlanmasıyla yürütme Modülü (EXE ya da DLL) yüklenmesi için iki ayrı mekanizma vardır: biri yönetilmeyen modülleri için kullanılır, Windows için ve biri için .NET ortak dil çalışma zamanı (.NET derlemelerini yükleyen CLR). Karışık DLL yükleme sorunu Microsoft Windows işletim sistemi yükleyicisi çevresinde toplanır.

Bir işlemine yalnızca .NET yapıları içeren bir derleme yüklendiğinde, CLR yükleyicisi tüm gerekli yükleme ve başlatma görevlerini kendisi gerçekleştirebilirsiniz. Yerel kod ve verileri içerebileceğinden ancak karışık derlemeler için Windows Yükleyici de kullanılması gerekir.

Windows Yükleyici kod erişebileceği erişim kodu ya da bu DLL verileri, başlatılmadan önce ve kısmen başlatıldığında hiçbir kod nedenle DLL yükleyebilir güvence altına alır. Bunu yapmak için Windows Yükleyici Modülü başlatma sırasında güvenli olmayan erişimi engelleyen ("Yükleyici kilidi" olarak da adlandırılır) bir işlem genel kritik bölüm kullanır. Sonuç olarak, yükleme işlemi birçok Klasik kilitlenme senaryosuna karşı savunmasızdır. Karışık derlemeler için aşağıdaki iki senaryo kilitlenme riski artırır:

- Kullanıcıların Microsoft Ara dili (MSIL) Yükleyici kilidi tutulurken derlenmiş işlevleri yürütmeyi çalışırsanız, ilk (gelen `DllMain` veya örneğin statik başlatıcılar içinde), bu kilitlenmeye neden olabilir. MSIL işlevi türü yüklenmemiş bir bütünleştirilmiş başvuruda bulunan bir durum düşünün. CLR yükleyici kilitte Windows Yükleyici gerektirebilecek Bu derlemeyi otomatik olarak yüklemeye çalışacaktır. Yükleyici kilidi çağrı sırası daha önce kodda tarafından zaten kilitli olduğundan, bir kilitlenme sonuçlanır. Ancak, yükleyici kilidi altında MSIL yürütme kilitlenme, tanılamak ve gidermek bu senaryo zorlaşır oluşacağını garanti etmez. Bazı durumlarda, başvurulan tür DLL içerdiği gibi hiçbir yerel yapılar ve tüm bağımlılıkları hiçbir yerel yapılar yükleyicisi başvurulan türün .NET derleme yükleme için gerekli olmayan Windows içerir. Ayrıca, gerekli derleme veya karma yerel/.NET bağımlılıklarını zaten başka bir kod tarafından yüklenmiş olabilir. Sonuç olarak, kilitlenmenin tahmin etmek zordur ve hedef makine yapılandırmasına bağlı olarak değişebilir.

- İkinci olarak, DLL'ler sürüm 1.0 ve 1.1 .NET Framework'ün yüklerken, yükleyici kilidi düzenlenmemiş olduğunu ve yükleyici kilidi altında geçersiz çeşitli eylemleri CLR varsayılır. Yükleyici kilidi düzenlenmemiş varsayarak bir geçerli önermesinin .NET DLL'leri varsayılır, ancak Karışık DLL'ler yerel başlatma yordamları yürüttüğünden, yerel Windows Yükleyicisi ve bu nedenle yükleyici kilidi gerektirir. Sonuç olarak, geliştirici DLL başlatma sırasında MSIL işlevleri yürütme girişiminde olsa bile, vardı hala sürüm 1.0 ve 1.1 .NET Framework'ün belirleyici kilitlenme küçük olasılığını.

Tüm gerekircilik karışık DLL yükleme işlemi kaldırılmıştır. Bu, bu değişiklikler ile gerçekleştirilmiştir:

- CLR Karışık DLL'ler yüklerken yanlış varsayımlar artık hale getirir.

- Yönetilen ve yönetilmeyen başlatma iki ayrı ve farklı aşamada gerçekleştirilir. Yönetilmeyen başlatma kurulur ilk (DllMain) ve yönetilen başlatma kurulur daha sonra üzerinden bir. NET desteklenen yapı olarak adlandırılan bir *.cctor*. İkincisi kullanıcıya tamamen saydam olacak sürece **/Zl** veya **/NODEFAULTLIB** kullanılır. Bkz:[/NODEFAULTLIB (kitaplıkları yoksay)](../build/reference/nodefaultlib-ignore-libraries.md) ve [/Zl (varsayılan kitaplık adını atla)](../build/reference/zl-omit-default-library-name.md) daha fazla bilgi için.

Yükleyici kilidi hala oluşabilir, ancak şimdi onu tekrarlanarak meydana gelir ve algılanır. Varsa `DllMain` MSIL yönergeler içeren derleyici uyarısı oluşturur [Derleyici Uyarısı (düzey 1) C4747](../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md). Ayrıca, CRT veya CLR algılamak ve yükleyici kilidi altında MSIL yürütmeyi denediğinde rapor çalışacaktır. CRT algılama sonuçları çalışma zamanında tanılama C çalışma zamanı hatası R6033 görülmesine neden olur.

Bu belgenin geri kalanında MSIL yükleyici kilidi altında yürütebilir kalan senaryolar çözümler için her biri bu senaryoları ve hata ayıklama teknikleri altında sorunu açıklanır.

## <a name="scenarios-and-workarounds"></a>Senaryolar ve geçici çözümler

Altında kullanıcı kodu yükleyici kilidi altında MSIL yürütebilir birçok farklı durum vardır. Geliştirici, kullanıcı kod uygulamasının bu şartların her biri altında MSIL yönergeleri yürütmek denemez emin olmalısınız. Aşağıdaki alt bölümleri yaygın durumlarda sorunların nasıl giderileceğini tartışması tüm olanaklarını açıklar.

### <a name="dllmain"></a>DllMain

`DllMain` İşlevi bir DLL için bir kullanıcı tanımlı giriş noktasıdır. Aksi takdirde, kullanıcının belirttiği sürece `DllMain` bir işlem veya iş parçacığı ekler veya içeren DLL'den ayırır her zaman çağrılır. Yükleyici kilidi tutulan olsa da, kullanıcı tarafından sağlanan Hayır bu çağrıyı meydana gelebileceğinden `DllMain` işlevi için MSIL derlenmiş. İşlev çağrısı ağacında köklü Ayrıca, `DllMain` için MSIL derlenebilir. Tanımlayan kod bloğunu Burada, sorunları gidermek için `DllMain` #pragma ile değiştirilmesi gereken `unmanaged`. Aynı her işlev için yapılmalıdır, `DllMain` çağrıları.

Burada, bu işlevler çağıran başka bağlamlarda için MSIL uygulaması gerektiren bir işlevini çağırmanız gerekir durumlarda, çoğaltma stratejisi hem .NET hem de aynı işlevi yerel sürümünü oluşturulduğu kullanılabilir.

Alternatif olarak, varsa `DllMain` gerekli değil veya bu loader altında yürütülecek gerekli değildir, kilitleme, kullanıcı tarafından sağlanan `DllMain` uygulaması kaldırılabilir, sorunun ortadan kaldırır.

DllMain doğrudan MSIL yürütme girişiminde bulunursa [Derleyici Uyarısı (düzey 1) C4747](../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md) neden olur. Ancak, derleyici, burada DllMain sırayla MSIL yürütmeyi denediğinde başka bir modülde bir işlevi çağırdığı durumları algılayamaz.

Bu senaryo hakkında daha fazla bilgi için lütfen "Engelleri için tanılama" bakın.

### <a name="initializing-static-objects"></a>Statik Nesneleri Başlatma

Dinamik bir başlatıcı gerekliyse statik nesneleri başlatma kilitlenmeyle sonuçlanabilir. Bu yüzden kilitlenme riski statik değişken yalnızca derleme zamanında bilinen bir değere atandığında gibi basit durumlar için hiç dinamik başlatma gereklidir. Ancak, işlev çağrıları, oluşturucu çağırmaları veya adresindeki değerlendirilemez ifadeleri tarafından başlatılan statik değişkenler derleme zamanı tüm modülü başlatma sırasında yürütmek için kodu gerektirir.

Aşağıdaki kod, dinamik başlatma gerektiren statik başlatıcıları örnekleri gösterir: bir işlev çağrısı, nesne oluşturması ve bir işaretçi başlatma. (Bu örneklerde statik değildir, ancak aynı etkiye sahip genel kapsamda tanımlanan varsayılır.)

```cpp
// dynamic initializer function generated
int a = init();
CObject o(arg1, arg2);
CObject* op = new CObject(arg1, arg2);
```

Bu kilitlenme riski olup olmadığını içeren modülü ile derlenmiş olup bağlıdır **/CLR** ve olup MSIL yürütülür. Özellikle, statik değişken olmadan derlenmiş ise **/CLR** (veya bir #pragma alıyor `unmanaged` blok), ve MSIL yönergeleri yürütülmesi sonuçlarında başlatmak için gerekli dinamik Başlatıcı kilitlenme oluşabilir. Bu olmadan derlenen modüller için çünkü **/CLR**, statik değişkenler başlatma DllMain tarafından gerçekleştirilir. Buna karşılık, ile statik değişkenler derlenmiş **/CLR** .cctor tarafından yönetilmeyen başlatma aşaması tamamlandıktan sonra yükleyici kilidi serbest başlatılır.

Statik değişkenler (sorunu gidermek için gereken süre sırada kabaca düzenlenmiş) dinamik başlatılması nedeni kilitlenme çözümleri vardır:

- Statik değişken içeren kaynak dosya ile derlenmiş **/CLR**.

- Yerel kod #pragma kullanarak statik değişkeni tarafından çağrılan tüm işlevler derlenebilir `unmanaged` yönergesi.

- El ile statik değişken, bir .NET ve yerel sürüm farklı adlara sahip sağlama bağlıdır kodu kopyalayın. Geliştiriciler yerel sürümü yerel statik başlatıcılardan ve .NET sürüm başka bir yerde çağırın.

### <a name="user-supplied-functions-affecting-startup"></a>Başlangıç etkileyen kullanıcı tarafından sağlanan işlevler

Birkaç kullanıcı tarafından sağlanan işlevleri kitaplıkları başlangıç sırasında başlatma için bağımlı vardır. Örneğin, genel C++ işleçleri gibi aşırı yüklendiğinde `new` ve `delete` işleçleri, kullanıcı tarafından sağlanan sürümler her yerde kullanılır, C++ Standart Kitaplığı Başlatma ve yok etme gibi. Sonuç olarak, C++ Standart Kitaplığı ve kullanıcı tarafından sağlanan statik başlatıcıları Bu işleçleri kullanıcı tarafından sağlanan tüm sürümlerini çağırır.

Kullanıcı tarafından sağlanan sürümler için MSIL derlenen, ardından bu başlatıcılar yükleyici kilidi kilitliyken MSIL yönergeleri yürütmek çalışıyor. Kullanıcı tarafından sağlanan `malloc` aynı sonuçları vardır. Bu sorunu gidermek için bu aşırı veya kullanıcı tarafından sağlanan tanımları #pragma kullanılarak yerel kod olarak uygulanmalıdır `unmanaged` yönergesi.

Bu senaryo hakkında daha fazla bilgi için lütfen "Engelleri için tanılama" bakın.

### <a name="custom-locales"></a>Özel yerel ayarlar

Kullanıcı bir özel genel yerel sağlarsa, bu yerel ayarlar da statik olarak başlatılır dahil olmak üzere, tüm gelecekteki g/ç akışlarını başlatmak için kullanılır. Bu genel yerel nesne için MSIL derlenmiş, yerel nesne üye işlevleri için MSIL derlenmiş yükleyici kilidi kilitliyken çağrılabilir.

Bu sorunu çözmek için üç seçenek vardır:

Tüm genel g/ç akış tanımları içeren kaynak dosyaları kullanarak derlenebilir **/CLR** seçeneği. Bu yükleyici kilidi altında çalıştırılmasını kendi statik başlatıcıları engeller.

Özel yerel ayar işlev tanımları #pragma kullanarak yerel koda derlenebilir `unmanaged` yönergesi.

Yükleyici kilidi serbest bırakıldıktan sonra özel yerel kadar genel yerel olarak ayarlamaktan kaçının. Daha sonra açıkça özel yerel ile başlatma sırasında oluşturulan g/ç akışlarını yapılandırın.

## <a name="impediments-to-diagnosis"></a>Tanılama engelleri

Bazı durumlarda kilitlenmelerin kaynağını tespit etmek zordur. Aşağıdaki alt bölümlerde, bu senaryoları ve bu sorunları çözmenin yolları açıklanmaktadır.

### <a name="implementation-in-headers"></a>Uygulama üst bilgileri

Select durumlarda üstbilgi dosyaları içindeki işlev uygulamaları tanılama karmaşık hale getirebilir. Satır içi işlevler ve şablon kodu işlevleri üstbilgi dosyasında belirtilmesini gerektirir.  C++ dili bir tanım anlam olarak eşdeğer olarak aynı ada sahip işlevlerin bütün uygulamalarında zorlar kural, belirtir. Sonuç olarak, C++ bağlayıcı herhangi diğer noktalar verilen işlevin yinelenen uygulamaları sahip nesne dosyaları birleştirilirken yapmamanız.

Visual Studio 2005 önce bağlayıcı basitçe farklı en iyi duruma getirme seçenekleri farklı kaynak dosyaları için kullanıldığında, iletme bildirimleri ve senaryoları uyum sağlamak için bu anlam olarak eşdeğer tanımları en büyük seçer. Bu karma yerel/.NET DLL'leri için bir sorun oluşturur.

Aynı başlığını olabileceğinden C++ dosyalarıyla tarafından her ikisi de dahil **/CLR** etkin ve devre dışı veya #include #pragma içinde kaydırılan `unmanaged` bloğu MSIL ve sağlayan İşlevler yerel sürümleri olması mümkündür üstbilgiler uygulamalarında. MSIL ve yerel uygulamalar etkili bir şekilde bir tanım kuralını ihlal ediyor yükleyici kilidi altında başlatma göre farklı semantiklerine sahip. Bağlayıcı en büyük uygulamayı seçtiğinde, açıkça başka bir yerde #pragma yönetilmeyen yönergesi kullanılarak yerel koda derlenen olsa bile sonuç olarak, bunu bir işlev MSIL sürümü seçebilirsiniz. Yükleyici kilidi altında bir şablonu veya satır içi işlev MSIL sürümü hiçbir zaman çağrıldığından emin olmak için her yükleyici kilidi altında her tür işlev tanımını #pragma değiştiren `unmanaged` yönergesi. Üst bilgi dosyasını üçüncü taraftan bunu elde etmenin en kolay yolu anında ve geçici #pragma yönetilmeyen yönergesi pop ise, #include yönergesi sorunlu üstbilgi dosyası için. (Bkz [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) bir örnek için.) Ancak, bu strateji .NET API'lerini doğrudan çağırmanız gerekir başka bir kod içeren üstbilgilerini çalışmaz.

Yükleyici kilidi ile ilgilenen kullanıcılar için bir kolaylık sunulduğunda yönetilen üzerinden yerel uygulama bağlayıcı seçeceksiniz. Yukarıdaki sorunları önler. Ancak, bu kuralın derleyicisi ile iki çözülmemiş bir sorun nedeniyle bu sürümde iki özel durum vardır:

- Satır içi bir çağrıdır bir genel statik işlev işaretçisi işlevdir. Sanal işlevler genel işlev işaretçileri çağrılır çünkü bu özellikle dikkat çekici bir senaryodur. Örneğin,
  
```cpp
#include "definesmyObject.h"
#include "definesclassC.h"

typedef void (*function_pointer_t)();

function_pointer_t myObject_p = &myObject;

#pragma unmanaged
void DuringLoaderlock(C & c)
{
    // Either of these calls could resolve to a managed implementation,
    // at link-time, even if a native implementation also exists.
    c.VirtualMember();
    myObject_p();
}
```

### <a name="diagnosing-in-debug-mode"></a>Hata ayıklama modunda tanılama

Yükleyici kilidi sorunları yapılmalıdır tüm tanıları Hata ayıklama derlemeleri. Yayın derlemeleri tanı oluşturmayabilir ve serbest bırakma modunda gerçekleştirilen iyileştirmeler yükleyici kilidi senaryolarında MSIL bazıları maskeleyebilir.

## <a name="how-to-debug-loader-lock-issues"></a>Yükleyici kilidi sorunlarını hata ayıklama

MSIL işlevi çağrıldığında, CLR oluşturan tanılama yürütme askıya almak CLR neden olur. Buna karşılık, bu Visual C++ karışık mod hata ayıklayıcı işlemdeki çalıştırırken de askıya alınmasına neden olur. Ancak, işleme eklerken, karma hata ayıklayıcıyı kullanma ayıklayıcı için yönetilen bir çağrı yığını almak mümkün değildir.

Yükleyici kilidi altında çağrıldı belirli MSIL işlevini tanımlamak için geliştiricilerin aşağıdaki adımları tamamlamanız gerekir:

1. Mscoree.dll ve mscorwks.dll kullanılabilir olduğundan emin olun.

   Bu iki yolla yapılabilir. İlk olarak, mscoree.dll ve mscorwks.dll pdb simge arama yoluna eklenebilir. Bunu yapmak için simge arama yolu seçenekleri iletişim kutusunu açın. (Gelen **Araçları** menüsünde seçin **seçenekleri**. Sol bölmesinde **seçenekleri** açık iletişim kutusunu **hata ayıklama** düğümü seçin **simgeleri**.) Yolun mscoree.dll ve mscorwks.dll PDB dosyaları arama listesine ekleyin. Bu pdb % VSINSTALLDIR%\SDK\v2.0\symbols yüklenir. Seçin **Tamam**.

   İkinci olarak, mscoree.dll ve mscorwks.dll pdb Microsoft Symbol Server'dan indirilebilir. Simge sunucusunu yapılandırmak için simge arama yolu seçenekleri iletişim kutusunu açın. (Gelen **Araçları** menüsünde seçin **seçenekleri**. Sol bölmesinde **seçenekleri** açık iletişim kutusunu **hata ayıklama** düğümü seçin **simgeleri**.) Arama listesini şu arama yolu Ekle: http://msdl.microsoft.com/download/symbols. Bir simge önbelleği dizini simge sunucusu önbelleği metin kutusuna ekleyin. Seçin **Tamam**.

1. Hata ayıklama modunu yalnızca yerel modu olarak ayarlanmış.

   Bunu yapmak için açın **özellikleri** çözümdeki başlangıç projesi için kılavuz. Seçin **yapılandırma özellikleri** > **hata ayıklama**. Ayarlama **hata ayıklayıcı türü** için **yalnızca yerel**.

1. Hata ayıklayıcı (F5) başlatın.
  
1. Zaman **/CLR** tanılama oluşturulur, seçin **yeniden deneme** ve ardından **sonu**.
  
1. Çağrı yığını penceresini açın. (Menü çubuğunda seçin **hata ayıklama** > **Windows** > **çağrı yığını**.) Sorunlu `DllMain` veya statik Başlatıcı yeşil bir ok ile tanımlanır. Soruna neden olan işlev tanımlanmadıysa bulmak için aşağıdaki adımlar izlenmelidir.

1. Açık **hemen** penceresi (menü çubuğunda seçin **hata ayıklama** > **Windows** > **hemen**.)

1. .Load sos.dll içine yazın **hemen** hata ayıklama hizmetini yüklemek için penceresi.
  
1. Türü! dumpstack **hemen** iç tam listesini almak için pencere **/CLR** yığını.

1. İlk örneği ya da _CorDllMain için (en yakın yığınının altına) bakın (varsa `DllMain` soruna neden olan) _VTableBootstrapThunkInitHelperStub ya da (statik Başlatıcı sorunu neden olursa) oluyorsa. Yığın hemen bu çağrının altına MSIL çağırma yükleyici kilidi altında yürütülmeye işlevi uygulanmadı girişidir.

1. Kaynak dosyaya gidin ve satır numarası önceki adımda tanımlanan ve doğru senaryoları ile senaryolar bölümünde açıklanan çözümler sorunu.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek kod taşıyarak yükleyici kilidi önlemek gösterilmiştir `DllMain` genel nesne oluşturucusu içine.

Bu örnekte, oluşturucuyu başlangıçtaki yönetilen nesne içeren genel bir yönetilen nesne yok `DllMain`. Bu örnek ikinci bölümü başlatmayı yapan modül oluşturucuyu çağırmak için yönetilen nesnesinin örneğini oluşturma derlemeye başvurur.

### <a name="code"></a>Kod

```cpp
// initializing_mixed_assemblies.cpp
// compile with: /clr /LD
#pragma once
#include <stdio.h>
#include <windows.h>
struct __declspec(dllexport) A {
   A() {
      System::Console::WriteLine("Module ctor initializing based on global instance of class.\n");
   }

   void Test() {
      printf_s("Test called so linker does not throw away unused object.\n");
   }
};

#pragma unmanaged
// Global instance of object
A obj;

extern "C"
BOOL WINAPI DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved) {
   // Remove all managed code from here and put it in constructor of A.
   return true;
}
```

Bu örnek karışık derlemeleri başlatma sorunları gösterir.

```cpp
// initializing_mixed_assemblies_2.cpp
// compile with: /clr initializing_mixed_assemblies.lib
#include <windows.h>
using namespace System;
#include <stdio.h>
#using "initializing_mixed_assemblies.dll"
struct __declspec(dllimport) A {
   void Test();
};

int main() {
   A obj;
   obj.Test();
}
```

Bu kod aşağıdaki çıktıyı üretir:

```Output
Module ctor initializing based on global instance of class.

Test called so linker does not throw away unused object.
```

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
