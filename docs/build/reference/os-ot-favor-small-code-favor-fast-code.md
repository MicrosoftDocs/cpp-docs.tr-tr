---
title: -Os, -Ot (küçük koda, hızlı koda ayrıcalık) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
dev_langs:
- C++
helpviewer_keywords:
- favor fast code compiler option [C++]
- /Os compiler option [C++]
- Ot compiler option [C++]
- /Ot compiler option [C++]
- small machine code
- -Ot compiler option [C++]
- fast code
- favor small code compiler option [C++]
- Os compiler option [C++]
- -Os compiler option [C++]
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f97ab0a53eb82b65149ea0f27139743e065f7ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378915"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os, /Ot (Küçük Koda Ayrıcalık Tanı, Hızlı Koda Ayrıcalık Tanı)
Simge durumuna küçültür veya exe ve DLL'ler boyutunu en üst düzeye çıkarır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Os  
/Ot  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/OS** (küçük koda ayrıcalık tanıma) boyutu hızından ayrıcalık tanıma derleyici yönlendirerek exe ve DLL'ler boyutunu azaltır. Derleyici birçok C ve C++ yapıları makine kodu işlevsel olarak benzer dizilerini azaltabilir. Bazen bu farklılıklar hızı karşı boyutunun bileşim sunar. **/Os** ve **/Ot** seçenekleri için diğer üzerinden tercih belirtmenize olanak tanır:  
  
 **/Ot** (hızlı koda ayrıcalık tanıma) en üst düzeye çıkarır exe ve DLL'ler hızına hızı boyutu ayrıcalık tanıma derleyici yönlendirerek. (Varsayılan değer budur.) Derleyici birçok C ve C++ yapıları makine kodu işlevsel olarak benzer dizilerini azaltabilir. Bazen bu farklılıklar hızı karşı boyutunun bileşim sunar. En üst düzeye hızına göre /Ot seçeneği kapsanan ([O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)) seçeneği. **O2** seçeneği çok hızlı kod üretmek için birkaç seçenek birleştirir.  
  
 Kullanırsanız **/Os** veya **/Ot**, sonra da belirtmeniz gerekir [/Og](../../build/reference/og-global-optimizations.md) kodu en iyi duruma getirme.  
  
> [!NOTE]
>  Test çalışmaları profil toplanan bilgileri geçersiz kılma belirtirseniz, aksi takdirde etkili olacak en iyi duruma getirme **/Ob**, **/Os**, veya **/Ot**. Daha fazla bilgi için [Profile-Guided en iyi duruma getirme](../../build/reference/profile-guided-optimizations.md).  
  
 **x86 belirli**  
  
 Aşağıdaki kod örneği küçük koda arasındaki farkı gösterir (**/Os**) seçenekleri ve ayrıcalık hızlı koda (**/Ot**) seçeneği:  
  
> [!NOTE]
>  Kullanırken aşağıdaki beklenen davranışını tanımlar **/Os** veya **/Ot**. Ancak, derleyici davranışı sürüm yayın farklı iyileştirmeler için aşağıdaki kodu neden olabilir.  
  
```  
/* differ.c  
  This program implements a multiplication operator  
  Compile with /Os to implement multiply explicitly as multiply.  
  Compile with /Ot to implement as a series of shift and LEA instructions.  
*/  
int differ(int x)  
{  
    return x * 71;  
}  
```  
  
 Makine kodu aşağıdaki parçasında gösterildiği gibi ne zaman DIFFER.c derlenmiş boyutu (**/Os**), derleyici uygular return deyimi bir ifadede çarpın açıkça olarak bir kod kısa ancak daha yavaş bir dizi Çarp üretmek için:  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
imul   eax, 71                  ; 00000047H  
```  
  
 Alternatif olarak, ne zaman DIFFER.c derlenmiş hızı (**/Ot**), derleyici uygular üst karakter dizisi olarak return deyimi bir ifadede çarpma ve `LEA` kodu hızlı ancak daha uzun bir dizi üretmek için yönergeler:  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
mov    ecx, eax  
shl    eax, 3  
lea    eax, DWORD PTR [eax+eax*8]  
sub    eax, ecx  
```  
  
 **Son x86 belirli**  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **en iyi duruma getirme** özellik sayfası.  
  
4.  Değiştirme **ayrıcalık boyutu veya hızı** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/O seçenekler (kodu İyileştir)](../../build/reference/o-options-optimize-code.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)