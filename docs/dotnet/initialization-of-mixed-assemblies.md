---
title: Karışık Derlemeleri Başlatma
description: Karma derlemelerin yüklenmesi ve başlatılması sırasında oluşabilecek sorunlarla uğraşın.
ms.date: 09/26/2020
helpviewer_keywords:
- mixed assemblies [C++], loader lock
- loader lock [C++]
- initializing mixed assemblies
- deadlocks [C++]
- .cctor [C++]
- custom locales [C++]
- mixed assemblies [C++], initilizing
ms.assetid: bfab7d9e-f323-4404-bcb8-712b15f831eb
ms.openlocfilehash: 6767e6087999138f8e62d3c5a58f972b4e2149ed
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413820"
---
# <a name="initialization-of-mixed-assemblies"></a>Karışık Derlemeleri Başlatma

Windows geliştiricileri, sırasında kod çalıştırılırken her zaman yükleyici kilidi olmalıdır `DllMain` . Ancak, C++/CLı karma mod Derlemeleriyle ilgilenirken göz önünde bulundurmanız gereken bazı ek sorunlar vardır.

[DllMain](/windows/win32/Dlls/dllmain) içindeki kodun .NET ortak dil çalışma zamanına (CLR) erişimi olmamalıdır. Diğer bir deyişle `DllMain` , yönetilen işlevlere doğrudan veya dolaylı olarak hiçbir çağrı yapılmamalıdır; hiçbir yönetilen kodun ' de bildirilmelidir veya uygulanması gerekmez; hiçbir `DllMain` çöp toplama veya otomatik kitaplık yüklemesi içinde gerçekleşmemelidir `DllMain` .

## <a name="causes-of-loader-lock"></a>Yükleyici kilidinin nedenleri

.NET platformunun tanıtılmasıyla birlikte, bir yürütme modülünü (EXE veya DLL) yüklemek için iki ayrı mekanizma vardır: bir Windows için, yönetilmeyen modüller için kullanılan ve bir diğeri de .NET derlemelerini yükleyen CLR için. Karışık DLL yükleme sorunu, Microsoft Windows işletim sistemi yükleyicisi etrafında yapılır.

Bir işleme yalnızca .NET yapılarını içeren bir derleme yüklendiğinde, CLR yükleyicisi tüm gerekli yükleme ve başlatma görevlerinin kendisini gerçekleştirebilir. Ancak, yerel kod ve veri içerebilen karışık derlemeler yüklemek için, Windows yükleyicisi de kullanılmalıdır.

Windows Yükleyici, başlatılmadan önce hiçbir kodun koda veya verilere erişemez olmasını garanti eder. Ayrıca, bir kodun kısmen başlatıldığı sırada DLL 'yi Redundantly yükleyememesini sağlar. Bunu yapmak için, Windows Yükleyici, modül başlatma sırasında güvenli olmayan erişimi önleyen, işlem küresel kritik bir bölüm (genellikle "yükleyici kilidi" olarak adlandırılır) kullanır. Sonuç olarak, yükleme işlemi klasik birçok kilitlenme senaryolarıyla savunmasızdır. Karışık derlemeler için aşağıdaki iki senaryo, kilitlenme riskini artırır:

- İlk olarak, kullanıcılar, yükleyici kilidi tutulduğunda ( `DllMain` Örneğin, statik başlatıcılardan veya statik başlatıcılarda) Microsoft ara dili (MSIL) için derlenen işlevleri yürütmeye çalışırsa, kilitlenme olabilir. MSIL işlevinin henüz yüklenmeyen bir derlemede bulunan bir türe başvurduğu durumu göz önünde bulundurun. CLR, bu derlemeyi otomatik olarak yüklemeye çalışır ve bu da Windows Yükleyici 'nin yükleyici kilidi üzerinde engellemesini gerektirebilir. Yükleyici kilidi çağrı dizisinde daha önce kodla zaten tutulduğundan kilitlenme oluşur. Ancak, yükleyici kilidi altında MSIL 'nin yürütülmesi bir kilitlenme oluşması garanti etmez. Bu, bu senaryonun tanılanması ve düzeltilmesi zor hale gelir. Bazı durumlarda, başvurulan türün DLL 'SI yerel yapı içermiyorsa ve tüm bağımlılıkları yerel yapı içermiyorsa, başvurulan türün .NET derlemesini yüklemek için Windows yükleyicisi gerekli değildir. Ayrıca, gerekli derleme veya karma yerel/. NET bağımlılıkları başka kod tarafından zaten yüklenmiş olabilir. Sonuç olarak, kilitlenerek tahmin edilmesi zor olabilir ve hedef makinenin yapılandırmasına bağlı olarak farklılık gösterebilir.

- İkincisi, .NET Framework sürüm 1,0 ve 1,1 ' de dll 'Leri yüklerken CLR, yükleyici kilidinin tutulmadığı kabul edilir ve yükleyici kilidi altında geçersiz olan birkaç eylem gerçekleştirmektedir. Yükleyici kilidinin tutulmadığından, tamamen .NET DLL 'Ler için geçerli bir varsayımdır. Ancak, karma dll 'Ler yerel başlatma yordamlarını yürüttiğinden, yerel Windows Yükleyicisi ve sonuç olarak yükleyici kilidi gerekir. Bu nedenle, geliştirici, DLL başlatma sırasında herhangi bir MSIL işlevini yürütmeye girişmese de, 1,0 ve 1,1 ' de .NET Framework sürümleri için çok sayıda belirleyici olmayan kilitlenme olasılığı vardır.

Kesin olmayan tüm maronciliği karışık DLL yükleme işleminden kaldırılmıştır. Şu değişikliklerle gerçekleştirildi:

- CLR artık karma dll 'Leri yüklerken yanlış varsayımlar yapmaz.

- Yönetilmeyen ve yönetilen başlatma iki ayrı ve farklı aşamada yapılır. Yönetilmeyen başlatma önce gerçekleşir (aracılığıyla `DllMain` ) ve yönetilen başlatma daha sonra bir ile gerçekleşir. NET destekli `.cctor` yapı. İkincisi, veya kullanılmadığı takdirde Kullanıcı tarafından tamamen saydamdır **`/Zl`** **`/NODEFAULTLIB`** . Daha fazla bilgi için bkz.[ `/NODEFAULTLIB` (kitaplıkları Yoksay)](../build/reference/nodefaultlib-ignore-libraries.md) ve [ `/Zl` (varsayılan kitaplık adını atla)](../build/reference/zl-omit-default-library-name.md).

Yükleyici kilidi yine de oluşabilir, ancak artık reproducibly olur ve algılanır. `DllMain`MSIL yönergeleri içeriyorsa, derleyici uyarı [derleyicisi Uyarısı (düzey 1) C4747](../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md)oluşturur. Ayrıca, CRT veya CLR, yükleyici kilidi altında MSIL yürütme girişimlerini algılamaya ve rapor kurmaya çalışacaktır. Çalışma zamanı tanılama C çalışma zamanı hatası R6033 içinde CRT algılama sonuçları.

Bu makalenin geri kalanında, MSIL 'in yükleyici kilidi altında yürütebileceği kalan senaryolar açıklanmaktadır. Bu senaryoların her birinde sorunun nasıl çözümleneceğini ve hata ayıklama tekniklerinin nasıl yapılacağını gösterir.

## <a name="scenarios-and-workarounds"></a>Senaryolar ve geçici çözümler

Kullanıcı kodunun, yükleyici kilidi altında MSIL yürütebileceği birkaç farklı durum vardır. Geliştirici, Kullanıcı kodu uygulamasının bu durumların her biri altında MSIL yönergelerini yürütmeye kalkışmayı denememesini sağlamalıdır. Aşağıdaki alt bölümlerde, en yaygın durumlarda sorunların nasıl çözümlenme hakkındaki bir Tartışmayla ilgili tüm olanaklar açıklanır.

### <a name="dllmain"></a>DllMain

`DllMain`İşlevi, DLL için Kullanıcı tanımlı bir giriş noktasıdır. Kullanıcı aksini belirtmediği sürece, `DllMain` bir işlem veya iş parçacığı IÇEREN dll 'ye her eklendiğinde veya bu bilgisayardan ayrıldığında çağrılır. Yükleyici kilidi tutulurken bu çağrı gerçekleşebildiği için, Kullanıcı tarafından sağlanan herhangi bir `DllMain` Işlev MSIL 'e derlenmemelidir. Ayrıca, üzerinde kök olarak belirtilen çağrı ağacında hiçbir işlev `DllMain` MSIL 'e derlenebilir. Buradaki sorunları çözmek için, tarafından tanımlanan kod bloğu `DllMain` ile değiştirilmelidir `#pragma unmanaged` . Çağıran her işlev için aynı yapılmalıdır `DllMain` .

Bu işlevlerin diğer çağırma bağlamları için MSIL uygulamasını gerektiren bir işlevi çağırması gereken durumlarda, aynı işlevin hem .NET hem de yerel sürümünün oluşturulduğu bir çoğaltma stratejisi kullanabilirsiniz.

Alternatif olarak, `DllMain` gerekli değilse veya yükleyici kilidi altında yürütülmesi gerekmiyorsa, Kullanıcı tarafından sağlanmış uygulamayı kaldırabilirsiniz, bu da `DllMain` sorunu ortadan kaldırır.

`DllMain`MSIL 'i doğrudan yürütmeye çalışırsa, [Derleyici Uyarısı (düzey 1) C4747](../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md) sonuç olarak sonuçlanır. Ancak derleyici, `DllMain` başka bir modülde işlev çağıran ve MSIL yürütme girişiminde bulunan durumları algılayamaz.

Bu senaryo hakkında daha fazla bilgi için bkz. [Tanılama ile](#impediments-to-diagnosis)ilgili daha fazla bilgi.

### <a name="initializing-static-objects"></a>Statik Nesneleri Başlatma

Dinamik bir başlatıcı gerekliyse statik nesnelerin başlatılması kilitlenmeyle sonuçlanabilir. Basit durumlar (örneğin, derleme zamanında bir statik değişkene bilinen bir değer atadığınızda) dinamik başlatma gerektirmez, bu nedenle kilitlenmenin riski yoktur. Ancak bazı statik değişkenler, işlev çağrıları, Oluşturucu etkinleştirmeleri veya derleme zamanında değerlendirilemeyen ifadeler tarafından başlatılır. Bu değişkenlerin hepsi modül başlatma sırasında yürütülmesi için kod gerektirir.

Aşağıdaki kodda dinamik başlatma gerektiren statik başlatıcıların örnekleri gösterilmektedir: bir işlev çağrısı, nesne oluşturma ve işaretçi başlatma. (Bu örnekler statik değildir, ancak aynı etkiye sahip olan genel kapsamda tanımlara sahip olduğu varsayılır.)

```cpp
// dynamic initializer function generated
int a = init();
CObject o(arg1, arg2);
CObject* op = new CObject(arg1, arg2);
```

Bu kilitlenme riski, kapsayan modülün ile derlenip derlenmediğine **`/clr`** ve MSIL 'in yürütülüp yürütülmeyeceğini bağlıdır. Özellikle, statik değişken olmadan **`/clr`** (veya bir `#pragma unmanaged` blokta) derlenirse ve bu işlemi başlatmak için gereken dinamik BAŞLATıCı, MSIL yönergelerinin yürütülmesi sonucunda, kilitlenme oluşabilir. Bunun nedeni, olmadan derlenen modüllerde **`/clr`** Statik değişkenlerin başlatılması DllMain tarafından gerçekleştirilir. Buna karşılık, ile derlenen statik değişkenler **`/clr`** tarafından başlatılır `.cctor` , yönetilmeyen başlatma aşaması tamamlandıktan sonra ve yükleyici kilidi serbest bırakılır.

Statik değişkenlerin dinamik başlatılmasına neden olan kilitlenmeye yönelik birkaç çözüm vardır. Sorunu çözmek için gereken süre içinde kabaca düzenlenirler:

- Statik değişkeni içeren kaynak dosya ile derlenebilir **`/clr`** .

- Statik değişken tarafından çağrılan tüm işlevler, yönergesi kullanılarak yerel koda derlenebilir `#pragma unmanaged` .

- Statik değişkenin bağımlı olduğu kodu, hem .NET hem de yerel bir sürümü farklı adlarla birlikte el ile kopyalayın. Geliştiriciler daha sonra yerel statik başlatıcılardan yerel sürümü çağırabilir ve .NET sürümünü başka bir yerde çağırabilir.

### <a name="user-supplied-functions-affecting-startup"></a>Başlatmayı etkileyen Kullanıcı tarafından sağlanan Işlevler

Başlangıç sırasında hangi kitaplıkların başlatılmasına bağlı olarak Kullanıcı tarafından sağlanan birkaç işlev vardır. Örneğin, ve işleçleri gibi C++ ' da işleçleri Global olarak aşırı **`new`** yüklerken **`delete`** , Kullanıcı tarafından belirtilen sürümler C++ Standart Kitaplığı başlatma ve yok etme dahil olmak üzere her yerde kullanılır. Sonuç olarak, C++ standart kitaplığı ve Kullanıcı tarafından sağlanmış statik başlatıcılar, bu işleçlerin Kullanıcı tarafından sağlanmış tüm sürümlerini çağırır.

Kullanıcı tarafından sağlanmış sürümler MSIL 'e derlenmişse, bu başlatıcılar yükleyici kilidi tutulurken MSIL yönergelerini yürütmeye çalışır. Kullanıcı tarafından sağlanan `malloc` sonuçlar aynı sonuçlara sahiptir. Bu sorunu çözmek için, bu aşırı yüklemelerin veya Kullanıcı tarafından sağlanan tanımların, yönergesi kullanılarak yerel kod olarak uygulanması gerekir `#pragma unmanaged` .

Bu senaryo hakkında daha fazla bilgi için bkz. [Tanılama ile](#impediments-to-diagnosis)ilgili daha fazla bilgi.

### <a name="custom-locales"></a>Özel yerel ayarlar

Kullanıcı özel bir genel yerel ayar sağlıyorsa, bu yerel ayar, statik olarak başlatılan akışlar dahil olmak üzere tüm gelecek g/ç akışlarını başlatmak için kullanılır. Bu genel yerel ayar nesnesi MSIL 'e derlenmişse, yükleyici kilidi tutulurken MSIL 'e derlenen yerel ayar nesnesi üye işlevleri çağrılabilir.

Bu sorunu çözmek için üç seçenek vardır:

Tüm genel g/ç akış tanımlarını içeren kaynak dosyalar, seçeneği kullanılarak derlenebilir **`/clr`** . Bu, statik başlatıcıların yükleyici kilidi altında yürütülmesini engeller.

Özel yerel ayar işlev tanımları, yönergesi kullanılarak yerel koda derlenebilir `#pragma unmanaged` .

Yükleyici kilidi yayımlanıncaya kadar özel yerel ayarı genel yerel ayar olarak ayarlamakten kaçının. Daha sonra, başlatma sırasında oluşturulan g/ç akışlarını özel yerel ayar ile açıkça yapılandırın.

## <a name="impediments-to-diagnosis"></a>Tanılama için engel

Bazı durumlarda kilitlenmeleri kaynağını tespit etmek zordur. Aşağıdaki alt bölümlerde bu senaryolar ve bu sorunları geçici olarak çözmek için yollar ele alınmaktadır.

### <a name="implementation-in-headers"></a>Üst bilgilerde uygulama

Seçim durumlarında, üst bilgi dosyaları içindeki işlev uygulamaları tanısı karmaşıklaştırır. Satır içi işlevlerin ve şablon kodunun her ikisi de bir başlık dosyasında belirtilmesini gerektirir.  C++ dili, aynı ada sahip tüm işlev uygulamalarını anlamsal olarak eşdeğer olacak şekilde zorlayan tek bir tanım kuralını belirtir. Sonuç olarak, C++ Bağlayıcısı belirli bir işlevin yinelenen uygulamalarına sahip nesne dosyalarını birleştirirken özel bir dikkat yapmamalıdır.

Visual Studio 2005 ' den önceki Visual Studio sürümlerinde bağlayıcı, bu anlamsal olarak denk tanımların en büyüğünü seçer. Farklı kaynak dosyaları için farklı iyileştirme seçenekleri kullanıldığında ileri bildirimlere ve senaryolarına uyum sağlamak için yapılır. Karma yerel ve .NET DLL 'Ler için bir sorun oluşturur.

Aynı üst bilgi hem etkin hem de devre dışı olan C++ dosyaları tarafından dahil edilebilir **`/clr`** veya bir #include bir blok içinde sarmalanabilir, `#pragma unmanaged` ancak üst bilgide uygulamalar sağlayan IŞLEVLERIN hem MSIL hem de yerel sürümlerinin olması mümkündür. MSIL ve yerel uygulamalar, bir tanım kuralını etkili bir şekilde ihlal eden yükleyici kilidi altında başlatma için farklı semantiklere sahiptir. Sonuç olarak, bağlayıcı en büyük uygulamayı seçtiğinde, yönergesi kullanılarak yerel koda açıkça derlense bile, bir işlevin MSIL sürümünü seçebiliriz `#pragma unmanaged` . Bir şablon veya satır içi işlevin MSIL sürümünün yükleyici kilidi altında hiçbir şekilde çağrılmeyeceğinden emin olmak için, yükleyici kilidi altında çağrılan her bir işlevin her tanımının, `#pragma unmanaged` yönergeyle değiştirilmesi gerekir. Üst bilgi dosyası üçüncü bir tarafdan ise, bu değişikliği yapmanın en kolay yolu, `#pragma unmanaged` soruna yol açan üst bilgi dosyasının #include yönergesinin etrafında Push ve açılır. (Bir örnek için bkz. [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) .) Ancak, bu strateji .NET API 'Lerini doğrudan çağırması gereken diğer kodu içeren Üstbilgiler için çalışmaz.

Yükleyici kilidi ile ilgilenen kullanıcılara kolaylık sağlamak için bağlayıcı, her ikisiyle de sunulmadığında yerel uygulamayı yönetilen üzerinde seçer. Bu varsayılan, yukarıdaki sorunları önler. Bununla birlikte, bu sürümde, derleyicinin iki çözümlenmemiş sorunu nedeniyle bu kuralın iki özel durumu vardır:

- Satır içi bir işleve yapılan çağrı, genel bir statik işlev işaretçisidir. Bu senaryo, sanal işlevler genel işlev işaretçileri aracılığıyla çağrıldığından tablo. Örneğin,

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

Yükleyici kilit sorunlarının tüm tanılar hata ayıklama Derlemeleriyle yapılmalıdır. Yayın yapıları tanılama oluşturmayabilir. Yayın modunda yapılan iyileştirmeler, yükleyici kilit senaryolarında bazı MSIL 'yi maskeleyebilir.

## <a name="how-to-debug-loader-lock-issues"></a>Yükleyici kilit sorunlarını ayıklama

Bir MSIL işlevi çağrıldığında CLR 'nin ürettiği tanı, CLR 'nin yürütmeyi askıya almasına neden olur. Bu durumda, Visual C++ karışık modda hata ayıklayıcının askıda olmasına ve hata ayıklanan işlem sırasında çalışmasına neden olur. Ancak, işleme eklenirken, karışık hata ayıklayıcı kullanılarak hata ayıklanan için yönetilen bir çağrı yığını elde etme olanağınız yok.

Yükleyici kilidi altında çağrılan belirli MSIL işlevini belirlemek için, geliştiriciler aşağıdaki adımları tamamlamalıdır:

1. mscoree.dll ve mscorwks.dll simgelerinin kullanılabilir olduğundan emin olun.

   Sembolleri iki şekilde kullanılabilir hale getirebilirsiniz. İlk olarak, mscoree.dll ve mscorwks.dll için pdb 'leri sembol arama yoluna eklenebilir. Bunları eklemek için sembol arama yolu seçenekleri iletişim kutusunu açın. ( **Araçlar** menüsünden **Seçenekler**' i seçin. **Seçenekler** iletişim kutusunun sol bölmesinde, **hata ayıklama** düğümünü açın ve **semboller**' i seçin.) Yolu mscoree.dll ve PDB dosyalarını mscorwks.dll arama listesine ekleyin. Bu PDB 'leri,%VSInstallDir%\sdk\v2.0\symboldizinine yüklenir. **Tamam ' ı**seçin.

   İkincisi, mscoree.dll ve mscorwks.dll için pdb 'leri Microsoft sembol sunucusundan indirilebilir. Sembol sunucusunu yapılandırmak için sembol arama yolu seçenekleri iletişim kutusunu açın. ( **Araçlar** menüsünden **Seçenekler**' i seçin. **Seçenekler** iletişim kutusunun sol bölmesinde, **hata ayıklama** düğümünü açın ve **semboller**' i seçin.) Bu arama yolunu arama listesine ekle: `https://msdl.microsoft.com/download/symbols` . Sembol sunucusu önbelleği metin kutusuna bir sembol önbellek dizini ekleyin. **Tamam ' ı**seçin.

1. Hata ayıklayıcı modunu yalnızca yerel moda ayarlayın.

   Çözümdeki başlangıç projesi için **Özellikler** kılavuzunu açın. **Yapılandırma özellikleri**  >  **hata ayıklamayı**seçin. **Hata ayıklayıcı türü** özelliğini **yalnızca yerel**olarak ayarlayın.

1. Hata ayıklayıcıyı başlatın (F5).

1. Tanılama oluşturulduğunda **`/clr`** **yeniden dene** ' yi ve ardından **Kes**' i seçin.

1. Çağrı yığını penceresini açın. (Menü çubuğunda **Hata Ayıkla**  >  ' yı seçin. **Windows**  >  **Çağrı yığını**.) Sorunlu `DllMain` veya statik Başlatıcı yeşil bir ok ile tanımlanır. Sorunlu işlev tanımlanmamışsa, bulmak için aşağıdaki adımların alınması gerekir.

1. **Hemen** penceresini açın (menü çubuğunda Windows anında **Hata Ayıkla**' yı seçin  >  **Windows**  >  **Immediate**.)

1. `.load sos.dll`Sos hata ayıklama hizmeti 'ni yüklemek Için **hemen** penceresine girin.

1. `!dumpstack`İç yığının tüm listesini almak Için **hemen** penceresine girin **`/clr`** .

1. _CorDllMain ( `DllMain` soruna neden olursa) veya _VTableBootstrapThunkInitHelperStub ya da GetTargetForVTableEntry (bir statik Başlatıcı soruna neden olursa) için ilk örneği (yığının en altına en yakın) arayın. Bu çağrının hemen altındaki yığın girdisi, yükleyici kilidi altında yürütülmeye çalışılan MSIL uygulanmış işlevin çağrıdır.

1. Önceki adımda tanımlanan kaynak dosya ve satır numarasına gidin ve senaryolar bölümünde açıklanan senaryoları ve çözümleri kullanarak sorunu giderin.

## <a name="example"></a>Örnek

### <a name="description"></a>Description

Aşağıdaki örnek, kodu `DllMain` bir genel nesnenin oluşturucusuna taşıyarak yükleyici kilidinin nasıl önleneceğini gösterir.

Bu örnekte, Oluşturucusu başlangıçta içinde olan yönetilen nesneyi içeren genel bir yönetilen nesne vardır `DllMain` . Bu örneğin ikinci bölümü, derlemeyi oluşturan modül oluşturucusunu çağırmak için yönetilen nesnenin bir örneğini oluşturarak derlemeye başvurur.

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
      printf_s("Test called so linker doesn't throw away unused object.\n");
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

Bu örnekte, karma derlemelerin başlatılmasında sorunlar gösterilmektedir:

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

Bu kod şu çıkışı oluşturur:

```Output
Module ctor initializing based on global instance of class.

Test called so linker doesn't throw away unused object.
```

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
