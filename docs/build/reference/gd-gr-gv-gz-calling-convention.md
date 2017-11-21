---
title: "-Gd, - Gr, - Gv, - Gz (çağırma kuralı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /gr
- /Gv
- /gz
- /Gd
- VC.Project.VCCLCompilerTool.CallingConvention
dev_langs: C++
helpviewer_keywords:
- -Gd compiler option [C++]
- -Gv compiler option [C++]
- /Gv compiler option [C++]
- -Gr compiler option [C++]
- Gd compiler option [C++]
- Gr compiler option [C++]
- /Gz compiler option [C++]
- -Gz compiler option [C++]
- /Gd compiler option [C++]
- Gz compiler option [C++]
- Gv compiler option [C++]
- /Gr compiler option [C++]
ms.assetid: fd3110cb-2d77-49f2-99cf-a03f9ead00a3
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9e06ca944768f8c4af2b207a75b923f5e1278943
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="gd-gr-gv-gz-calling-convention"></a>/Gd, /Gr, /Gv, /Gz (Çağırma Kuralı)
Bu seçenekler çağıran işlevi veya çağrılan işlev çağrısı sonunu yığında bağımsız değişkenleri kaldırır olup olmadığını hangi işlev bağımsız değişkenleri yığına gönderilen düzenini ve derleyici tanımlamak için kullandığı ad dekorasyon kuralı belirler tekil işlevler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Gd  
/Gr  
/Gv  
/Gz  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/Gd**, varsayılan ayar belirtir [__cdecl](../../cpp/cdecl.md) C++ üye dışındaki tüm işlevler için İşlevler ve işaretlenmiş işlevleri çağırma [__stdcall](../../cpp/stdcall.md), [__ Fastcall](../../cpp/fastcall.md), veya [__vectorcall](../../cpp/vectorcall.md).  
  
 **/Gr** belirtir `__fastcall` adlı işlevler için C++ üye işlevleri dışındaki tüm işlevleri çağırma kuralı, `main`ve işaretlenmiş işlevleri `__cdecl`, `__stdcall`, veya `__vectorcall`. Tüm `__fastcall` işlev prototipleri olması gerekir. Bu çağırma yalnızca x86 hedef derleyicileri içinde kullanılabilir ve diğer mimarileri hedef derleyicileri tarafından göz ardı edilir.  
  
 **/GZ** belirtir `__stdcall` adlı işlevler için C++ üye işlevleri dışındaki tüm işlevleri çağırma kuralı, `main`ve işaretlenmiş işlevleri `__cdecl`, `__fastcall`, veya `__vectorcall`. Tüm `__stdcall` işlev prototipleri olması gerekir. Bu çağırma yalnızca x86 hedef derleyicileri içinde kullanılabilir ve diğer mimarileri hedef derleyicileri tarafından göz ardı edilir.  
  
 **/ GV** belirtir `__vectorcall` işlevleri adlandırılmış ana, ile işlevleri için C++ üye işlevleri dışındaki tüm işlevleri çağırma kuralı, bir `vararg` değişken bağımsız değişken listesi veya çakışan ile işaretlenmiş işlevleri `__cdecl`, `__stdcall`, veya `__fastcall` özniteliği. Bu çağırma /arch:SSE2 destek x86 hem x64 mimarileri ve üzeri yalnızca kullanılabilir ve ARM mimarisi hedef derleyicileri tarafından göz ardı edilir.  
  
 Değişken sayıda bağımsız değişken almayan işlevleri işaretlenmelidir `__cdecl`.  
  
 **/Gd**, **/Gr**, **/GV** ve **/Gz** ile uyumlu değil [/CLR: safe](../../build/reference/clr-common-language-runtime-compilation.md) veya   **/CLR: pure**. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
> [!NOTE]
>  Varsayılan olarak x86 için işlemci, C++ üye işlevlerini kullanmak [__thiscall](../../cpp/thiscall.md).  
  
 Tüm işlemciler, açıkça olarak işaretlenmiş bir üye işlevi `__cdecl`, `__fastcall`, `__vectorcall`, veya `__stdcall` ilgili mimaride dikkate gerekiyorsa belirtilen çağırma kullanır. Değişken sayıda bağımsız değişken kullandığı her zaman alan bir üye işlevi `__cdecl` çağırma.  
  
 Bu derleyici seçenekleri Adlandır C++ yöntemleri ve işlevler üzerinde etkisi yoktur. Olarak bildirilir sürece `extern "C"`, C++ yöntemleri ve işlevlerini farklı bir ad dekorasyon düzenini kullanın. Daha fazla bilgi için bkz: [donatılmış adları](../../build/reference/decorated-names.md).  
  
 Çağırma kuralları hakkında daha fazla bilgi için bkz: [çağırma kuralları](../../cpp/calling-conventions.md).  
  
## <a name="cdecl-specifics"></a>__cdecl özellikleri  
 X86 üzerinde işlemciler, tüm işlev bağımsız değişkenleri geçirilir yığında sağdan sola. ARM ve x64 mimariler, bazı bağımsız değişkenler kaydı ile geçirilir ve rest sağdan sola yığında geçirilir. Yordamı çağrılırken bağımsız değişkenler yığından açılır.  
  
 C `__cdecl` işlev adı kuralı kullandığı adlandırma öncesinde bir çizgiyle ( `_` ); büyük/küçük harfe çeviri gerçekleştirilir. Olarak bildirilir sürece `extern "C"`, C++ işlevlerini farklı bir ad dekorasyon düzenini kullanın. Daha fazla bilgi için bkz: [donatılmış adları](../../build/reference/decorated-names.md).  
  
## <a name="fastcall-specifics"></a>__fastcall özellikleri  
 Bazı bir `__fastcall` işlevin bağımsız değişken Yazmaçları geçirilir (x86 için işlemciler, ECX ve EDX), ve rest kalan yığına sağdan sola. Bunu döndürmeden önce çağrılan yordamı bu bağımsız değişkenler yığından açılır. Genellikle, **/Gr** yürütme süresini azaltır.  
  
> [!NOTE]
>  Kullanırken dikkatli olun `__fastcall` satır içi derleme dilde herhangi bir işlev için çağırma. Yazmaçları kullanımınız derleyicinin kullanmaya çakışıyor.  
  
 C `__fastcall` işlev adı kuralı kullandığı adlandırma öncesinde bir at işareti (`@`) işlev bağımsız değişkenleri bayt cinsinden boyutu arkasından. Servis talebi çeviri yapılır. Derleyici bu şablon için adlandırma kuralı kullanır:  
  
```  
@function_name@number  
```  
  
 Kullandığınızda `__fastcall` dosyaları içeren standart adlandırma kuralını kullanın. Aksi takdirde, çözümlenmemiş dış başvuruları alırsınız.  
  
## <a name="stdcall-specifics"></a>__stdcall özellikleri  
 A `__stdcall` işlevin bağımsız değişkenleri gönderilen yığına sağdan sola ve onu döndürmeden önce bu bağımsız değişkenler yığından çağrılan işlev açılır.  
  
 C `__stdcall` işlev adı kuralı kullandığı adlandırma öncesinde bir çizgiyle ( `_` ) ve arkasından bir at işareti (@) ve işlev bağımsız değişkenleri bayt cinsinden boyutu. Servis talebi çeviri gerçekleştirilir. Derleyici bu şablon için adlandırma kuralı kullanır:  
  
```  
_functionname@number  
```  
  
## <a name="vectorcall-specifics"></a>__vectorcall özellikleri  
 A `__vectorcall` işlevin tamsayı bağımsız değişkenler (üzerinde x86) iki veya dört (üzerinde x64) kadar kullanarak değeriyle geçirilir tamsayı kaydeder ve en fazla altı XMM kayıtları için kayan nokta ve vektör değerleri ve rest geçirilir yığında sağdan sola. Bunu döndürmeden önce çağrılan işlev yığını temizler. Vektör ve kayan nokta dönüş değerleri XMM0'döndürülür.  
  
 C `__vectorcall` adlandırma kuralı iki işaretlerini (@@) ve işlev bağımsız değişkenleri bayt cinsinden boyutu işlevi adından kullanır. Servis talebi çeviri gerçekleştirilir. Derleyici bu şablon için adlandırma kuralı kullanır:  
  
```  
functionname@@number  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Seçin **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **arama kuralı** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)