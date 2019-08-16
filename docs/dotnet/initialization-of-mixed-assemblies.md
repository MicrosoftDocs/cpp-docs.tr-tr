---
title: Karışık Derlemeleri Başlatma
ms.date: 03/09/2018
helpviewer_keywords:
- mixed assemblies [C++], loader lock
- loader lock [C++]
- initializing mixed assemblies
- deadlocks [C++]
- .cctor [C++]
- custom locales [C++]
- mixed assemblies [C++], initilizing
ms.assetid: bfab7d9e-f323-4404-bcb8-712b15f831eb
ms.openlocfilehash: 35dd47bd87c278d60fc616dca854bf843acc7c57
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501233"
---
# <a name="initialization-of-mixed-assemblies"></a>Karışık Derlemeleri Başlatma

Windows geliştiricileri, sırasında `DllMain`kod çalıştırılırken her zaman yükleyici kilidi olmalıdır. Ancak,/clr karışık mod Derlemeleriyle C++ilgilenirken göz önünde bulundurmanız gereken bazı ek sorunlar vardır.

[DllMain](/windows/win32/Dlls/dllmain) içindeki kodun .NET ortak dil çalışma zamanına (CLR) erişimi olmamalıdır. Diğer bir deyişle, yönetilen işlevlere doğrudan veya dolaylı olarak hiçbir çağrı yapılmamalıdır; yönetilen kod ' de `DllMain`bildirilmelidir ve uygulanmaz; hiçbir çöp toplama veya otomatik kitaplık yükleme `DllMain` `DllMain` .

## <a name="causes-of-loader-lock"></a>Yükleyici kilidinin nedenleri

.NET platformunun tanıtılmasıyla birlikte, bir yürütme modülünü (EXE veya DLL) yüklemek için iki ayrı mekanizma vardır: bir Windows için, yönetilmeyen modüller için kullanılan ve bir diğeri de .NET derlemelerini yükleyen CLR için. Karışık DLL yükleme sorunu, Microsoft Windows işletim sistemi yükleyicisi etrafında yapılır.

Bir işleme yalnızca .NET yapılarını içeren bir derleme yüklendiğinde, CLR yükleyicisi tüm gerekli yükleme ve başlatma görevlerinin kendisini gerçekleştirebilir. Ancak, karma derlemeler için yerel kod ve veri içerebildiğinden, Windows yükleyicisi de kullanılmalıdır.

Windows Yükleyici, hiçbir kodun başlatılmadan önce bu DLL 'deki koda veya verilere erişe, aksi durumda hiçbir kodun kısmen başlatıldığı sırada DLL 'yi yükleyeredundantly. Bunu yapmak için, Windows Yükleyici, modül başlatma sırasında güvenli olmayan erişimi önleyen, işlem küresel kritik bir bölüm (genellikle "yükleyici kilidi" olarak adlandırılır) kullanır. Sonuç olarak, yükleme işlemi klasik birçok kilitlenme senaryolarıyla savunmasızdır. Karışık derlemeler için aşağıdaki iki senaryo, kilitlenme riskini artırır:

- İlk olarak, kullanıcılar, yükleyici kilidi tutulduğunda (örneğin, statik başlatıcılardan `DllMain` veya statik başlatıcılarda) Microsoft ara dili (MSIL) için derlenen işlevleri yürütmeye çalışırsa, kilitlenme olabilir. MSIL işlevinin yüklenmeyen bir derlemede bir türe başvurduğu durumu göz önünde bulundurun. CLR, bu derlemeyi otomatik olarak yüklemeye çalışır ve bu da Windows Yükleyici 'nin yükleyici kilidi üzerinde engellemesini gerektirebilir. Yükleyici kilidi çağrı dizisinde daha önce kodla zaten tutulduğundan kilitlenme oluşur. Ancak, yükleyici kilidi altında MSIL yürütmek, bu senaryonun tanılanması ve düzeltilmesi zor hale getiren bir kilitlenmenin gerçekleşmeyeceğini garanti etmez. Bazı durumlarda, başvurulan türün DLL 'SI yerel yapı içermiyorsa ve tüm bağımlılıkları yerel yapı içermiyorsa, başvurulan türün .NET derlemesini yüklemek için Windows yükleyicisi gerekli değildir. Ayrıca, gerekli derleme veya karma yerel/. NET bağımlılıkları başka kod tarafından zaten yüklenmiş olabilir. Sonuç olarak, kilitlenerek tahmin edilmesi zor olabilir ve hedef makinenin yapılandırmasına bağlı olarak farklılık gösterebilir.

- İkincisi, .NET Framework sürüm 1,0 ve 1,1 ' de dll 'Leri yüklerken CLR, yükleyici kilidinin tutulmadığından ve yükleyici kilidi altında geçersiz olan birkaç eylemi gerçekleştirdiğini kabul ediyor. Yükleyici kilidinin tutulmadığı varsayılarak, tamamen .NET DLL 'Leri için geçerli bir varsayımdır, ancak karma dll 'Ler yerel başlatma yordamlarını yürüttiğinden, yerel Windows Yükleyicisi ve bu nedenle yükleyici kilidi gerekir. Sonuç olarak, geliştirici DLL başlatma sırasında herhangi bir MSIL işlevini yürütmeye çalışmıyor olsa bile, .NET Framework 1,0 ve 1,1 sürümleri ile çok sayıda belirleyici olmayan bir kilitlenme olasılığı vardır.

Kesin olmayan tüm maronciliği karışık DLL yükleme işleminden kaldırılmıştır. Şu değişikliklerle gerçekleştirildi:

- CLR artık karma dll 'Leri yüklerken yanlış varsayımlar yapmaz.

- Yönetilmeyen ve yönetilen başlatma iki ayrı ve farklı aşamada gerçekleştirilir. Yönetilmeyen başlatma önce gerçekleşir (DllMain aracılığıyla) ve yönetilen başlatma daha sonra bir ile gerçekleşir. NET destekli `.cctor` yapı. **/Zl** veya **/nodefaultlib** kullanılmadığı takdirde ikinci Kullanıcı tarafından tamamen saydamdır. Daha fazla bilgi için bkz.[/nodefaultlib (kitaplıkları Yoksay)](../build/reference/nodefaultlib-ignore-libraries.md) ve [/zl (varsayılan kitaplık adını atla)](../build/reference/zl-omit-default-library-name.md) .

Yükleyici kilidi yine de oluşabilir, ancak artık reproducibly olur ve algılanır. MSIL yönergeleri içeriyorsa, derleyici uyarı [derleyicisi Uyarısı (düzey 1) C4747](../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md)oluşturur. `DllMain` Ayrıca, CRT veya CLR, yükleyici kilidi altında MSIL yürütme girişimlerini algılamaya ve rapor kurmaya çalışacaktır. Çalışma zamanı tanılama C çalışma zamanı hatası R6033 içinde CRT algılama sonuçları.

Bu belgenin geri kalanında, MSIL 'nin yükleyici kilidi altında yürütebileceği kalan senaryolar, bu senaryoların her birinde sorun için çözümler ve hata ayıklama teknikleri açıklanmaktadır.

## <a name="scenarios-and-workarounds"></a>Senaryolar ve geçici çözümler

Kullanıcı kodunun, yükleyici kilidi altında MSIL yürütebileceği birkaç farklı durum vardır. Geliştirici, Kullanıcı kodu uygulamasının bu durumların her biri altında MSIL yönergelerini yürütmeye kalkışmadığından emin olmalıdır. Aşağıdaki alt bölümlerde, en yaygın durumlarda sorunların nasıl çözümlenme hakkındaki bir Tartışmayla ilgili tüm olanaklar açıklanır.

### <a name="dllmain"></a>DllMain

`DllMain` İşlevi, DLL için Kullanıcı tanımlı bir giriş noktasıdır. Kullanıcı aksini belirtmediği sürece, `DllMain` bir işlem veya iş parçacığı içeren dll 'ye her eklendiğinde veya bu bilgisayardan ayrıldığında çağrılır. Yükleyici kilidi tutulurken bu çağrı gerçekleşebildiği için, Kullanıcı tarafından sağlanan `DllMain` herhangi bir işlev MSIL 'e derlenmemelidir. Ayrıca, üzerinde `DllMain` kök olarak belirtilen çağrı ağacında hiçbir işlev MSIL 'e derlenebilir. Buradaki sorunları çözmek için, tanımlayan `DllMain` kod bloğu #pragma `unmanaged`ile değiştirilmelidir. `DllMain` Çağıran her işlev için aynı yapılmalıdır.

Bu işlevlerin diğer çağırma bağlamları için MSIL uygulamasını gerektiren bir işlevi çağırması gereken durumlarda, bir çoğaltma stratejisi aynı işlevin hem .NET hem de yerel bir sürümünün oluşturulduğu yerde kullanılabilir.

Alternatif olarak, `DllMain` gerekli değilse veya yükleyici kilidi altında yürütülmesi gerekmiyorsa, Kullanıcı tarafından sağlanmış `DllMain` uygulama kaldırılabilir, bu da sorunu ortadan kaldırır.

DllMain MSIL 'i doğrudan yürütmeye çalışırsa, [Derleyici Uyarısı (düzey 1) C4747](../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md) sonuç olarak sonuçlanır. Ancak, derleyici, DllMain 'in daha sonra MSIL yürütme girişiminde bulunduğu başka bir modülde bir işlevi çağırdığı durumları algılayamaz.

Bu senaryo hakkında daha fazla bilgi için bkz. [Tanılama ile](#impediments-to-diagnosis)ilgili daha fazla bilgi.

### <a name="initializing-static-objects"></a>Statik Nesneleri Başlatma

Dinamik bir başlatıcı gerekliyse statik nesnelerin başlatılması kilitlenmeyle sonuçlanabilir. Statik bir değişken derleme zamanında bilinen bir değere atandığında olduğu gibi basit durumlarda, hiçbir dinamik başlatma gerekmez, bu nedenle kilitlenmenin bir riski yoktur. Bununla birlikte, işlev çağrıları, Oluşturucu etkinleştirmeleri veya derleme zamanında değerlendirilemeyen ifadeler, modül başlatma sırasında kodun yürütülmesi gerekir.

Aşağıdaki kodda dinamik başlatma gerektiren statik başlatıcıların örnekleri gösterilmektedir: bir işlev çağrısı, nesne oluşturma ve işaretçi başlatma. (Bu örnekler statik değildir, ancak aynı etkiye sahip olan genel kapsamda tanımlandığı varsayılır.)

```cpp
// dynamic initializer function generated
int a = init();
CObject o(arg1, arg2);
CObject* op = new CObject(arg1, arg2);
```

Bu kilitlenme riski, kapsayan modülün **/clr** ile derlenip derlenmeyeceğini ve MSIL 'in yürütülüp yürütülmeyeceğini bağlıdır. Özellikle, statik değişken **/clr** olmadan (veya bir #pragma `unmanaged` bloğunda) derlenirse ve bu işlemi başlatmak için gereken dinamik başlatıcı, MSIL yönergelerinin yürütülmesi sonucunda, kilitlenme oluşabilir. Bunun nedeni, **/clr**olmadan derlenen modüller için statik değişkenlerin başlatılması DllMain tarafından gerçekleştirilir. Buna karşılık, **clr** ile derlenen statik değişkenler, `.cctor`yönetilmeyen başlatma aşaması tamamlandıktan ve yükleyici kilidi yayımlandıktan sonra tarafından başlatılır.

Statik değişkenlerin dinamik olarak başlatılmasının neden olduğu kilitlenme için çok sayıda çözüm vardır (sorunun giderilmesi için gereken süre içinde kabaca düzenlenir):

- Statik değişkeni içeren kaynak dosya **/clr**ile derlenebilir.

- Statik değişken tarafından çağrılan tüm işlevler, #pragma `unmanaged` yönergesi kullanılarak yerel koda derlenebilir.

- Statik değişkenin bağımlı olduğu kodu, hem .NET hem de yerel bir sürümü farklı adlarla birlikte el ile kopyalayın. Geliştiriciler daha sonra yerel statik başlatıcılardan yerel sürümü çağırabilir ve .NET sürümünü başka bir yerde çağırabilir.

### <a name="user-supplied-functions-affecting-startup"></a>Başlatmayı etkileyen Kullanıcı tarafından sağlanan Işlevler

Başlangıç sırasında hangi kitaplıkların başlatılmasına bağlı olarak Kullanıcı tarafından sağlanan birkaç işlev vardır. Örneğin, C++ `new` ve `delete` işleçleri gibi işleçlerini genel olarak aşırı yüklerken, Kullanıcı tarafından belirtilen sürümler C++ standart kitaplık başlatma ve yok etme dahil olmak üzere her yerde kullanılır. Sonuç olarak, standart C++ kitaplık ve Kullanıcı tarafından sağlanmış statik başlatıcılar, bu işleçlerin Kullanıcı tarafından sağlanmış tüm sürümlerini çağırır.

Kullanıcı tarafından sağlanmış sürümler MSIL 'e derlenmişse, bu başlatıcılar yükleyici kilidi tutulurken MSIL yönergelerini yürütmeye çalışır. Kullanıcı tarafından sağlanan `malloc` sonuçlar aynı sonuçlara sahiptir. Bu sorunu çözmek için, bu aşırı yüklemelerin veya Kullanıcı tarafından sağlanan tanımların #pragma `unmanaged` yönergesini kullanarak yerel kod olarak uygulanması gerekir.

Bu senaryo hakkında daha fazla bilgi için bkz. [Tanılama ile](#impediments-to-diagnosis)ilgili daha fazla bilgi.

### <a name="custom-locales"></a>Özel yerel ayarlar

Kullanıcı özel bir genel yerel ayar sağlıyorsa, bu yerel ayar, statik olarak başlatılan akışlar dahil olmak üzere tüm gelecek g/ç akışlarını başlatmak için kullanılacaktır. Bu genel yerel ayar nesnesi MSIL 'e derlenmişse, yükleyici kilidi tutulurken MSIL 'e derlenen yerel ayar nesnesi üye işlevleri çağrılabilir.

Bu sorunu çözmek için üç seçenek vardır:

Tüm genel g/ç akış tanımlarını içeren kaynak dosyalar **/clr** seçeneği kullanılarak derlenebilir. Bu, statik başlatıcıların yükleyici kilidi altında yürütülmesini engeller.

Özel yerel ayar işlev tanımları, #pragma `unmanaged` yönergesi kullanılarak yerel koda derlenebilir.

Yükleyici kilidi yayımlanıncaya kadar özel yerel ayarı genel yerel ayar olarak ayarlamakten kaçının. Daha sonra, başlatma sırasında oluşturulan g/ç akışlarını özel yerel ayar ile açıkça yapılandırın.

## <a name="impediments-to-diagnosis"></a>Tanılama için engel

Bazı durumlarda kilitlenmeleri kaynağını tespit etmek zordur. Aşağıdaki alt bölümlerde bu senaryolar ve bu sorunları geçici olarak çözmek için yollar ele alınmaktadır.

### <a name="implementation-in-headers"></a>Üst bilgilerde uygulama

Seçim durumlarında, üst bilgi dosyaları içindeki işlev uygulamaları tanısı karmaşıklaştırır. Satır içi işlevlerin ve şablon kodunun her ikisi de bir başlık dosyasında belirtilmesini gerektirir.  C++ Dil, aynı ada sahip tüm işlev uygulamalarını anlamsal olarak eşdeğer olacak şekilde zorlayan tek bir tanım kuralını belirtir. Sonuç olarak, C++ bağlayıcı belirli bir işlevin yinelenen uygulamalarına sahip nesne dosyalarını birleştirirken özel bir dikkat sunmamalıdır.

Visual Studio 2005 ' den önce bağlayıcı, farklı kaynak dosyaları için farklı en iyi duruma getirme seçenekleri kullanılırken iletme bildirimlerini ve senaryolarını sağlamak için bu anlamsal denk tanımlardan en büyük birini seçer. Karma yerel/. NET DLL 'Ler için bir sorun oluşturur.

Aynı üst bilgi her ikisi de **/clr** özellikli ve C++ devre dışı bırakılmış dosyalarla birlikte dahil edilebilir veya bir #include bir `#pragma unmanaged` blok içinde sarmalanabilir bilgisinde. MSIL ve yerel uygulamalar, bir tanım kuralını etkili bir şekilde ihlal eden yükleyici kilidi altında başlatmaya göre farklı semantiklere sahiptir. Sonuç olarak, bağlayıcı en büyük uygulamayı seçtiğinde, #pragma yönetilmeyen yönergeyi kullanan başka bir yerde yerel koda derlense bile, bir işlevin MSIL sürümünü seçebiliriz. Bir şablon veya satır içi işlevin MSIL sürümünün yükleyici kilidi altında hiçbir şekilde çağrılmeyeceğinden emin olmak için, yükleyici kilidi altında çağrılan her bir işlevin her tanımının, `#pragma unmanaged` yönergeyle değiştirilmesi gerekir. Üst bilgi dosyası üçüncü bir tarafdan ise, bu değişikliği yapmanın en kolay yolu, soruna yol açan üst bilgi dosyasının #include `#pragma unmanaged` yönergesinin etrafında Push ve açılır. (Bir örnek için bkz. [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) .) Ancak, bu strateji .NET API 'Lerini doğrudan çağırması gereken diğer kodu içeren Üstbilgiler için çalışmaz.

Yükleyici kilidi ile ilgilenen kullanıcılara kolaylık sağlamak için bağlayıcı, her ikisiyle de sunulmadığında yerel uygulamayı yönetilen üzerinde seçer. Bu varsayılan, yukarıdaki sorunları önler. Ancak, bu yayında, derleyici ile ilgili çözümlenmemiş sorunlar nedeniyle bu kuralın iki özel durumu vardır:

- Satır içi bir işleve yapılan çağrı, genel bir statik işlev işaretçisidir. Bu senaryo, sanal işlevler genel işlev işaretçileri aracılığıyla çağrıldığı için önemli ' dır. Örneğin,

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

Yükleyici kilit sorunlarının tüm tanılar hata ayıklama Derlemeleriyle yapılmalıdır. Yayın yapıları tanılama oluşturmayabilir ve yayın modunda gerçekleştirilen iyileştirmeler, yükleyici kilit senaryolarında bazı MSIL 'yi maskeleyebilir.

## <a name="how-to-debug-loader-lock-issues"></a>Yükleyici kilit sorunlarını ayıklama

Bir MSIL işlevi çağrıldığında CLR 'nin ürettiği tanı, CLR 'nin yürütmeyi askıya almasına neden olur. Ayrıca, bu, Visual C++ karışık mod hata ayıklayıcının askıya alınmasına ve hata ayıklanan işlem sırasında çalışmasına neden olur. Ancak, işleme eklenirken, karışık hata ayıklayıcı kullanarak hata ayıklama için yönetilen bir çağrı yığını elde etmek mümkün değildir.

Yükleyici kilidi altında çağrılan belirli MSIL işlevini belirlemek için, geliştiriciler aşağıdaki adımları tamamlamalıdır:

1. Mscoree. dll ve mscorwks. dll simgelerinin kullanılabilir olduğundan emin olun.

   Sembolleri iki şekilde kullanılabilir hale getirebilirsiniz. İlk olarak, mscoree. dll ve mscorwks. dll için pdb 'leri sembol arama yoluna eklenebilir. Bunları eklemek için sembol arama yolu seçenekleri iletişim kutusunu açın. ( **Araçlar** menüsünden **Seçenekler**' i seçin. **Seçenekler** iletişim kutusunun sol bölmesinde, **hata ayıklama** düğümünü açın ve **semboller**' i seçin.) Mscoree. dll ve mscorwks. dll PDB dosyalarının yolunu arama listesine ekleyin. Bu PDB 'leri,%VSInstallDir%\sdk\v2.0\symboldizinine yüklenir. **Tamam**’ı seçin.

   İkincisi, mscoree. dll ve mscorwks. dll için pdb 'leri Microsoft sembol sunucusundan indirilebilir. Sembol sunucusunu yapılandırmak için sembol arama yolu seçenekleri iletişim kutusunu açın. ( **Araçlar** menüsünden **Seçenekler**' i seçin. **Seçenekler** iletişim kutusunun sol bölmesinde, **hata ayıklama** düğümünü açın ve **semboller**' i seçin.) Bu arama yolunu arama listesine ekle: `https://msdl.microsoft.com/download/symbols`. Sembol sunucusu önbelleği metin kutusuna bir sembol önbellek dizini ekleyin. **Tamam**’ı seçin.

1. Hata ayıklayıcı modunu yalnızca yerel moda ayarlayın.

   Çözümdeki başlangıç projesi için **Özellikler** kılavuzunu açın. **Yapılandırma özellikleri** > **hata ayıklamayı**seçin. **Hata ayıklayıcı türünü** **yalnızca yerel**olarak ayarlayın.

1. Hata ayıklayıcıyı başlatın (F5).

1. **/Clr** tanısı oluşturulduğunda **yeniden dene** ' yi ve ardından **Kes**' i seçin.

1. Çağrı yığını penceresini açın. (Menü çubuğunda > **Windows** > **çağrı yığını** **Hata Ayıkla**' yı seçin.) Sorunlu `DllMain` veya statik Başlatıcı yeşil bir ok ile tanımlanır. Sorunlu işlev tanımlanmamışsa, bulmak için aşağıdaki adımların alınması gerekir.

1. **Hemen** penceresini açın (menü çubuğunda**Windows** > **anında** **Hata Ayıkla** > ' yı seçin.)

1. SOS `.load sos.dll` hata ayıklama hizmeti 'ni yüklemek için **hemen** penceresine girin.

1. İç `!dumpstack` **/clr** yığınının tüm listesini almak için **hemen** penceresine girin.

1. _CorDllMain (soruna neden olursa `DllMain` ) veya _VTableBootstrapThunkInitHelperStub ya da GetTargetForVTableEntry (bir statik Başlatıcı soruna neden olursa) için ilk örneği (yığının en altına en yakın) arayın. Bu çağrının hemen altındaki yığın girdisi, yükleyici kilidi altında yürütülmeye çalışılan MSIL uygulanmış işlevin çağrıdır.

1. Önceki adımda tanımlanan kaynak dosya ve satır numarasına gidin ve senaryolar bölümünde açıklanan senaryoları ve çözümleri kullanarak sorunu giderin.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, kodu `DllMain` bir genel nesnenin oluşturucusuna taşıyarak yükleyici kilidinin nasıl önleneceğini gösterir.

Bu örnekte, Oluşturucusu başlangıçta içinde `DllMain`olan yönetilen nesneyi içeren genel bir yönetilen nesne vardır. Bu örneğin ikinci bölümü, derlemeyi oluşturan modül oluşturucusunu çağırmak için yönetilen nesnenin bir örneğini oluşturarak derlemeye başvurur.

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

Bu kod aşağıdaki çıktıyı üretir:

```Output
Module ctor initializing based on global instance of class.

Test called so linker does not throw away unused object.
```

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
