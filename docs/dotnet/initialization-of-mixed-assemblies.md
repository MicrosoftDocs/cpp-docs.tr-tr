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
ms.openlocfilehash: 05ffa5ba838b28764afb4ab7f30411ad786227f8
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344177"
---
# <a name="initialization-of-mixed-assemblies"></a>Karışık Derlemeleri Başlatma

Windows geliştiricileri her zaman olmalıdır yükleyici kilidi temkinli sırasında kod çalıştırırken `DllMain`. Ancak, ile işlem yapılırken dikkate alınması gereken bazı ek sorunlar vardır C++/CLR karma mod derlemeler.

İçinde kod [DllMain](/windows/desktop/Dlls/dllmain) .NET ortak dil çalışma zamanı (CLR) erişmemelidir. Bu anlamına `DllMain` yönetilen işlevlerine çağrı yapmanız gerekir, doğrudan veya dolaylı olarak; yönetilen kod yok bildirilemez veya uygulanan `DllMain`; ve çöp toplama ya da otomatik kitaplık yükleme içinde gerçekleşmesi gereken `DllMain` .

## <a name="causes-of-loader-lock"></a>Yükleyici kilidi nedenleri

.NET platformu sunulmasıyla birlikte, bir yürütme Modülü (EXE veya DLL) yüklenmesi için iki farklı mekanizma vardır: biri yönetilmeyen modüller için kullanılan Windows ve diğeri için CLR .NET derlemelerini yükler. Karışık DLL yükleme sorunu Microsoft Windows işletim sistemi yükleyicisi çevresinde toplanır.

Bir işleme yalnızca .NET yapıları içeren bir derleme yüklendiğinde, CLR yükleyici tüm gerekli yükleme ve başlatma görevleri kendisini gerçekleştirebilirsiniz. Yerel kod ve veriler içerebileceğinden ancak karışık derlemeler için Windows Yükleyici de kullanılması gerekir.

Windows Yükleyici kod erişebileceği erişim kodu veya DLL içindeki verileri, başlatılmadan önce ve kısmen başlatıldığında kod nedenle DLL yükleyebilir güvence altına alır. Yapmak için Windows Yükleyici Modülü başlatma sırasında güvenli olmayan erişimi engelleyen (genellikle "Yükleyici kilidi" olarak da adlandırılır) bir işlem genel kritik bölüm kullanır. Sonuç olarak, yükleme işlemi için birçok Klasik kilitlenme senaryoları daha savunmasızdır. Karışık derlemeler için aşağıdaki iki senaryoda kilitlenme riski artırın:

- Yükleyici kilidi tutulurken, Microsoft Ara dili (MSIL) derlenen işlevlerde yürütmek kullanıcıların çalışırsanız, ilk (gelen `DllMain` veya örneğin statik başlatıcılar), kilitlenmeye neden olabilir. MSIL işlevi yüklenmemiş bir derlemedeki bir türe başvuran bir durum düşünün. CLR yükleyici kilidi engellemek için Windows Yükleyici gerektirebilecek Bu derlemeyi otomatik olarak yük dener. Yükleyici kilidi zaten daha önce çağrı sırası içindeki kod tarafından tutulduğundan karşılıklı bir kilitlenme oluşur. Ancak, yükleyici kilidi altında MSIL yürütmek karşılıklı bir kilitlenme, bu senaryo, tanılamak ve gidermek daha zor yapar gerçekleşeceğini garanti etmez. Başvurulan tür DLL içerdiğinde hiçbir yerel yapıları hiçbir yerel yapılar ve tüm bağımlılıklarını içeren gibi bazı durumlarda, Windows Yükleyicisi başvurulan tür, .NET derlemesini yüklemek için gerekli değildir. Ayrıca, gerekli bütünleştirilmiş kodu veya karma yerel/.NET bağımlılıklarını zaten başka bir kod tarafından yüklenmiş olabilir. Sonuç olarak, kilitlenmenin tahmin etmek zor olabilir ve hedef makine yapılandırmasına bağlı olarak değişebilir.

- İkinci olarak, DLL'ler sürümleri 1.0 ve 1.1 .NET Framework'ün yüklerken, yükleyici kilidi düzenlenmemiş olduğunu ve yükleyici kilidi altında geçersiz çeşitli eylemleri CLR varsayılır. Yükleyici kilidi açık tutulduğu değil varsayarak bir tamamen .NET DLL'leri için geçerli varsayılır, ancak karışık DLL yerel başlatma yordamlarını yürüttüğünden, yerel Windows Yükleyici ve bu nedenle yükleyici kilidi gerektirir. Sonuç olarak, geliştirici MSIL işlevleri DLL başlatma sırasında yürütme girişiminde bile oluştu hala sürümleri 1.0 ve 1.1 .NET Framework'ün belirleyici olmayan kilitlenme küçük olanağı.

Karışık DLL yükleme işlemi tüm gerekircilik kaldırıldı. Bu değişikliklerle bu gerçekleştirilebilir:

- CLR, bundan böyle karışık DLL yüklenirken yanlış varsayım yapmaz.

- Yönetilen ve yönetilmeyen başlatma ayrı ve farklı iki aşamada gerçekleştirilir. Yönetilmeyen başlatma gerçekleşir ilk (DllMain) ve yönetilen başlatma gerçekleşir aracılığıyla daha sonra bir. NET desteklenen `.cctor` oluşturun. Son kullanıcıya tamamen şeffaftır sürece **/Zl** veya **/nodefaultlıb** kullanılır. Bkz:[/nodefaultlıb (kitaplıkları yoksay)](../build/reference/nodefaultlib-ignore-libraries.md) ve [/Zl (varsayılan kitaplık adını atla)](../build/reference/zl-omit-default-library-name.md) daha fazla bilgi için.

Yükleyici kilidi ortaya çıkabilir, ancak artık tekrarlanarak gerçekleşir ve algılanır. Varsa `DllMain` MSIL yönergeleri içeren bir derleyici uyarısı oluşturur [Derleyici Uyarısı (düzey 1) C4747](../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md). Ayrıca, CRT veya CLR algılayıp yükleyici kilidi altında MSIL yürütmek için rapor çalışacaktır. CRT algılama sonuçları çalışma zamanında tanılama C çalışma zamanı hatası R6033.

Bu belgenin geri kalanında MSIL yükleyici kilidi altında yürütebilir kalan senaryoları çözümler için sorun altında her biri bu senaryoları ve hata ayıklama teknikleri açıklar.

## <a name="scenarios-and-workarounds"></a>Senaryolar ve geçici çözümler

Altında kullanıcı kod yükleyici kilidi altında MSIL yürütebilir birkaç farklı durumlar vardır. Geliştirici, kullanıcı kodu uygulama her Bu koşullar altında MSIL yönergeleri yürütmek denemez emin olmanız gerekir. Aşağıdaki alt bölümlerde tüm olasılıkları en yaygın durumlarda sorunların nasıl giderileceğini açıklar.

### <a name="dllmain"></a>DllMain

`DllMain` İşlevi, bir kullanıcı tarafından tanımlanan giriş noktası bir DLL için kullanılabilir. Aksi takdirde, kullanıcının belirttiği sürece `DllMain` bir işlem veya iş parçacığı ekler veya içeren DLL dosyasından ayırır her zaman çağrılır. Bu çağrıyı yükleyici kilidi tutulan karşın, kullanıcı tarafından sağlanan yok oluşabilir beri `DllMain` işlevi, MSIL olarak derlenmiş. Hiçbir işlev çağrı ağacı köklü ayrıca `DllMain` MSIL olarak derlenmiş. Burada, sorunları tanımlar kod bloğu çözmek için `DllMain` #pragma ile değiştirilmelidir `unmanaged`. Her işlev için aynı yapılmalıdır, `DllMain` çağırır.

Burada, bu işlevlerin diğer arama bağlamı için MSIL uygulaması gerektiren bir işlevini çağırmanız gerekir durumlarda, bir çoğaltma stratejisi hem .NET hem de aynı işlevi yerel sürümünü oluşturulduğu kullanılabilir.

Alternatif olarak, varsa `DllMain` gerekli değil veya bunun altında yükleyici yürütülecek gerekli değildir, kilitleme, kullanıcı tarafından sağlanan `DllMain` uygulama kaldırılabilir, sorunu ortadan kaldırır.

DllMain MSIL doğrudan yürütmeyi denerse [Derleyici Uyarısı (düzey 1) C4747](../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md) neden olur. Ancak, derleyici burada DllMain sırayla MSIL yürütmeyi denerse, başka bir modül içinde bir işlevi çağırır durumları algılayamaz.

Bu senaryo hakkında daha fazla bilgi için bkz. [tanılama aksaklıkları](#impediments-to-diagnosis).

### <a name="initializing-static-objects"></a>Statik Nesneleri Başlatma

Statik nesneleri başlatma, dinamik bir başlatıcı gerekiyorsa kilitlenmeyle neden olabilir. Kilitlenme riski olması için bir statik değişken derleme zamanında bilinen bir değere atandığında gibi basit durumlar, hiçbir dinamik başlatma gereklidir. Bununla birlikte, işlev çağrıları, oluşturucu çağrılarını veya değerlendirilemeyen ifadeler tarafından başlatılmış statik değişkenler derleme zamanı tüm modülü başlatma sırasında yürütmek için kodu gerektirir.

Aşağıdaki kod, dinamik olarak başlatılması gerektiren statik başlatıcılar örneklerini gösterir: bir işlev çağrısı, nesne oluşturması ve bir işaretçi başlatma. (Bu örnekleri statik olmayan, ancak aynı etkiye sahip genel kapsamda tanımlı olarak kabul edilir.)

```cpp
// dynamic initializer function generated
int a = init();
CObject o(arg1, arg2);
CObject* op = new CObject(arg1, arg2);
```

Bu kilitlenme riski olup olmadığını içeren modülü ile derlenmiş olup bağlıdır **/CLR** ve MSIL olup yürütülür. Özellikle statik değişkeni olmadan derlenirse **/CLR** (veya bir #pragma içinde yer alıyor `unmanaged` blok), ve sonuçları MSIL yönergeleri yürütülmesini başlatmak için gerekli dinamik Başlatıcı Kilitlenme ortaya çıkabilir. Bu olmadan derlenen modüller için çünkü **/CLR**, statik değişkenlerin başlatması DllMain tarafından gerçekleştirilir. Buna karşılık, ile statik değişkenler derlenmiş **/CLR** tarafından başlatılan `.cctor`, yönetilmeyen başlatma aşaması tamamlandıktan sonra yükleyici kilidi serbest.

Statik değişkenler (sorunu gidermek için gereken süre sırasına göre kabaca düzenlenmiş) dinamik olarak başlatılması nedeniyle kilitlenme çözümleri vardır:

- Statik değişken içeren kaynak dosya ile derlenmiş **/CLR**.

- #Pragma kullanılarak yerel kod için statik değişkeni tarafından çağrılan tüm işlevlerin derlenebilir `unmanaged` yönergesi.

- El ile statik değişken bağlıdır, hem .NET hem de yerel sürüm farklı adlara sahip sağlama kodu kopyalayın. Geliştiriciler yerel sürüm yerel statik başlatıcılardan ve başka bir yerde .NET sürümünü arayın.

### <a name="user-supplied-functions-affecting-startup"></a>Başlangıç etkileyen kullanıcı tarafından sağlanan işlevleri

Birden fazla kullanıcı tarafından sağlanan işlevleri kitaplıklarını başlatma başlatma sırasında bağımlı vardır. Örneğin, genel olarak gibi C++'daki işleçler aşırı yüklendiğinde `new` ve `delete` işleçleri, kullanıcı tarafından sağlanan sürümleri her yerde kullanılır, C++ Standart Kitaplığı Başlatma ve yok edilmesini içerir. Sonuç olarak, C++ Standart Kitaplığı ve kullanıcı tarafından sağlanan statik başlatıcılar bu işleçler kullanıcı tarafından sağlanan tüm sürümlerini çağırır.

Kullanıcı tarafından sağlanan sürümleri MSIL olarak derlenir, ardından bu başlatıcıları yükleyici kilidi açık tutulduğu sürece MSIL yönergeleri yürütmek çalışıyor. Bir kullanıcı tarafından sağlanan `malloc` aynı sonuçları vardır. Bu sorunu gidermek için bu aşırı yüklemeleri veya kullanıcı tarafından sağlanan tanımları #pragma kullanılarak yerel kod uygulanması gereken `unmanaged` yönergesi.

Bu senaryo hakkında daha fazla bilgi için bkz. [tanılama aksaklıkları](#impediments-to-diagnosis).

### <a name="custom-locales"></a>Özel yerel ayarlar

Genel bir özel yerel kullanıcı sağlar, bu yerel statik olarak başlatılan akışlar da dahil olmak üzere, tüm gelecek g/ç akışları başlatmak için kullanılır. Bu genel yerel ayar nesnesi, MSIL olarak derlenmiş, MSIL olarak derlenmiş yerel ayar nesnesi üye işlevleri yükleyici kilidi açık tutulduğu sürece çağrılabilir.

Bu sorunu çözmek için üç seçenek vardır:

Tüm genel g/ç akışı tanımlarını içeren kaynak dosyalarını kullanarak derlenebilir **/CLR** seçeneği. Kendi statik başlatıcılar yükleyici kilidi altında çalıştırılmasını engeller.

#Pragma kullanarak yerel kod için özel yerel işlev tanımları derlenebilir `unmanaged` yönergesi.

Yükleyici kilidi serbest bırakıldıktan sonra özel yerel ayar olarak genel yerel ayarlamaktan kaçının. Daha sonra açıkça özel yerel ayar ile başlatma sırasında oluşturulan g/ç akışları yapılandırın.

## <a name="impediments-to-diagnosis"></a>Tanılama aksaklıkları

Bazı durumlarda, kilitlenmeleri kaynağını tespit etmek zordur. Aşağıdaki alt bölümlerde bu senaryolar ve bu sorunların çözüm yolları açıklanmaktadır.

### <a name="implementation-in-headers"></a>Üst uygulama

Seçili durumlarda, üst bilgi dosyaları içindeki işlev uygulamaları tanılama karmaşık hale getirebilir. Satır içi işlevleri ve şablon kodunun işlevleri bir üstbilgi dosyasında belirtilmesi gerekir.  C++ dili tek tanım anlamsal olarak eşdeğer olarak aynı ada sahip İşlevler'in tüm uygulamalarından zorlar kuralı belirtir. Sonuç olarak, C++ bağlayıcı tüm özel durumlar yinelenen uygulamaları, belirli bir işlevi olan nesne dosyaları birleştirilirken yapmamanız.

Visual Studio 2005'ten önce bağlayıcı yalnızca iletme bildirimleri ve senaryolar için farklı kaynak dosyaları farklı iyileştirme seçenekleri kullanıldığında uyum sağlamak için bu anlamsal olarak eşdeğer tanımlara en büyük seçer. Bunu, karma yerel/.NET DLL'ler için sorun oluşturur.

Aynı üst bilgiyi olabilir çünkü her ikisi için de dahil C++ ile dosyaları **/CLR** etkin ve devre dışı veya #include içinde sarmalanmış bir `#pragma unmanaged` bloğu MSIL hem sağlayan işlevlerin yerel sürümleri olması mümkündür uygulamaları üst. MSIL ve yerel uygulamaları etkili bir şekilde tek tanım kuralı ihlal yükleyici kilidi altında başlatma farklı semantiklere sahip. Bağlayıcı en büyük uygulama seçtiğinde, açıkça başka bir yerde yönetilmeyen #pragma yönergesi kullanarak yerel koda derlenen bile sonuç olarak, bu işlevin MSIL sürümünü tercih edebilirsiniz. Bir MSIL sürüm bir şablon veya satır içi işlevinin, yükleyici kilidi altında hiçbir zaman çağrılır emin olmak için her yükleyici kilidi altında gibi her bir işlevin tanımı ile değiştirilmelidir `#pragma unmanaged` yönergesi. Üst bilgi dosyası üçüncü bir taraftan, bu değişikliği yapmak için en kolay yolu gönderme ve açılan ise `#pragma unmanaged` etrafında yönerge #include yönergesi sorunlu üstbilgi dosyası için. (Bkz [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) bir örnek.) Ancak, bu strateji, .NET API'lerini doğrudan çağırmanız gerekir başka bir kod içeren üst bilgiler için çalışmaz.

Yükleyici kilidi ile ilgilenen kullanıcılar için bir kolaylık olarak sunulduğunda yönetilen üzerinden yerel uygulama bağlayıcı seçersiniz. Bu varsayılan yukarıdaki sorunları önler. Ancak, bu kuralın derleyicisi ile iki çözülmemiş sorunları nedeniyle bu sürümde iki istisna mevcuttur:

- Satır içi işlev çağrısı bir genel statik işlev işaretçisidir. Sanal işlevler genel işlev işaretçileri olarak adlandırılır çünkü bu önemli bir senaryodur. Örneğin,

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

Hata ayıklama sorunları yapılmalıdır yükleyici kilidi tüm tanıları oluşturur. Yayın derlemeleri tanılama vermeyebilir ve yayın modunda yapılan iyileştirmeler, bazı yükleyici kilidi senaryolarında MSIL maskeleyebilir.

## <a name="how-to-debug-loader-lock-issues"></a>Yükleyici kilidi sorunlarında hata ayıklama

Bir MSIL işlevi çağrıldığında, CLR oluşturan tanılama yürütmeyi askıya almak CLR neden olur. Buna karşılık, görsel neden C++ işlemdeki hata ayıklanan çalışırken de askıya için karışık mod hata ayıklayıcı. Ancak, işleme iliştirirken karma hata ayıklayıcısını kullanarak hata ayıklanan için yönetilen bir çağrı yığını almak mümkün değildir.

Geliştiriciler, yükleyici kilidi altında çağrıldı belirli bir MSIL işlev tanımlamak için aşağıdaki adımları tamamlamanız gerekir:

1. Mscoree.dll ve kullanımda olan mscorwks.dll'ye kullanılabilir olduğundan emin olun.

   Simgeler iki şekilde kullanılabilir hale getirebilirsiniz. İlk olarak, pdb mscoree.dll ve kullanımda olan mscorwks.dll'ye için Sembol arama yolu eklenebilir. Bunları eklemek için Sembol arama yolu Seçenekler iletişim kutusunu açın. (Gelen **Araçları** menüsünde seçin **seçenekleri**. Sol bölmesinde **seçenekleri** açık iletişim kutusunu **hata ayıklama** düğüm ve **sembolleri**.) Yolun mscoree.dll ve kullanımda olan mscorwks.dll'ye PDB dosyaları arama listesine ekleyin. Bu pdb % VSINSTALLDIR%\SDK\v2.0\symbols yüklenir. **Tamam**’ı seçin.

   İkinci olarak, pdb mscoree.dll ve kullanımda olan mscorwks.dll'ye Microsoft sembol sunucusundan indirilebilir. Sembol sunucusu yapılandırmak için Sembol arama yolu Seçenekler iletişim kutusunu açın. (Gelen **Araçları** menüsünde seçin **seçenekleri**. Sol bölmesinde **seçenekleri** açık iletişim kutusunu **hata ayıklama** düğüm ve **sembolleri**.) Bu arama yolu arama listesine ekleyin: `https://msdl.microsoft.com/download/symbols`. Sembol önbellek dizini sembol sunucusu önbellek metin kutusuna ekleyin. **Tamam**’ı seçin.

1. Hata ayıklayıcı modu yalnızca yerel moda ayarlayın.

   Açık **özellikleri** çözüm başlangıç projesi için kılavuz. Seçin **yapılandırma özellikleri** > **hata ayıklama**. Ayarlama **hata ayıklayıcı türü** için **yalnızca yerel**.

1. Hata ayıklayıcı (F5) başlatın.

1. Zaman **/CLR** tanılama oluşturulur, seçin **yeniden** seçip **sonu**.

1. Çağrı yığını penceresini açın. (Menü çubuğunda, **hata ayıklama** > **Windows** > **çağrı yığını**.) Sorunlu `DllMain` veya statik Başlatıcı, yeşil bir ok ile tanımlanır. Sorunlu işlevi tanımlanmamışsa bulmak için aşağıdaki adımları alınması gerekir.

1. Açık **hemen** penceresinde (menü çubuğunda, **hata ayıklama** > **Windows** > **hemen**.)

1. Girin `.load sos.dll` içine **hemen** penceresi hata ayıklama hizmetini yüklemek için.

1. Girin `!dumpstack` içine **hemen** iç tam listesini almak için pencere **/CLR** yığını.

1. İlk örneğinin ya da _CorDllMain için (en yakın yığın altına) bakın (varsa `DllMain` soruna neden olan) _VTableBootstrapThunkInitHelperStub ya da oluyorsa (statik bir başlatıcı soruna neden olursa). Yükleyici kilidi altında yürütülmeye çalışıldı işlevin MSIL çağırmayı uygulanan hemen altındaki Bu çağrı yığını girdisi var.

1. Kaynak dosyaya gidin ve satır numarası önceki adımda tanımlanan ve doğru senaryoları ile senaryoları bölümünde açıklanan çözümler sorunu.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, koddan taşıyarak yükleyici kilidi önlemek gösterilmektedir `DllMain` içine bir genel nesnesinin Oluşturucusu.

Bu örnekte, Oluşturucusu başlangıçtaki yönetilen nesneyi içeren genel bir yönetilen nesne yok `DllMain`. Bu örnek ikinci bölümü başlatma yapan modül oluşturucuyu çağırmak için yönetilen nesneye bir örneğini oluşturarak derlemeye başvuruyor.

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

Bu örnek, karışık derlemeleri başlatma sorunları göstermektedir:

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
