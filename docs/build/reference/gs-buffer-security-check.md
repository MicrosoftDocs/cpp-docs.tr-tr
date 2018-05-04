---
title: -GS (arabellek güvenlik denetimi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BufferSecurityCheck
- VC.Project.VCCLCompilerTool.BufferSecurityCheck
- /GS
dev_langs:
- C++
helpviewer_keywords:
- buffers [C++], buffer overruns
- buffer overruns, compiler /GS switch
- GS compiler option [C++]
- /GS compiler option [C++]
- security check compiler option [C++]
- -GS compiler option [C++]
- buffers [C++], avoiding overruns
ms.assetid: 8d8a5ea1-cd5e-42e1-bc36-66e1cd7e731e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aa1204a6959121b3f6280433c0414f81c038548
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="gs-buffer-security-check"></a>/GS (Arabellek Güvenlik Denetimi)  
  
Bir işlevin dönüş adresi, özel durum işleyici adresi ya da belirli türde bir parametre üzerine bazı arabellek taşmaları algılar. Arabellek Taşması neden arabellek boyutu kısıtlamaları zorlamaz kod yararlanmak için saldırganlar tarafından kullanılan bir tekniktir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/GS[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
  
**/GS** varsayılan olarak açıktır. Uygulamanızı hiçbir güvenlik açıklarını olmasını bekliyorsanız kullanmak **/GS-**. Hakkında daha fazla bilgi için **/GS**, bkz: [içinde derleyici güvenlik derinliği denetler](http://go.microsoft.com/fwlink/p/?linkid=7260). Arabellek Taşması algılamasını gizleme hakkında daha fazla bilgi için bkz: [safebuffers](../../cpp/safebuffers.md).  
  
## <a name="security-checks"></a>Güvenlik denetimleri  
  
Arabellek taşması sorunları gibi tabi derleyicisi tanır İşlevler, derleyici dönüş adresi önce yığın üzerinde alan ayırır. İşlev girişinde ayrılan alanı ile yüklenen bir *güvenlik tanımlama bilgisi* , hesaplanan bir kez modülü yük. İşlev Çıkışta ve 64-bit işletim sistemlerinde çerçeve geriye doğru izleme sırasında yardımcı işlev tanımlama bilgisinin değeri hala aynı olduğundan emin olmak için çağrılır. Farklı bir değer yığınının üzerine yazmaya oluşmuş olabilir gösterir. Farklı bir değer algılanırsa, işlem sonlandırıldı.  
  
## <a name="gs-buffers"></a>GS arabellekler  
  
Arabellek Taşması Güvenlik denetimi gerçekleştirilir bir *GS arabellek*. GS arabellek bunlardan biri olabilir:  
  
-   4 bayttan büyük bir dizi ikiden fazla öğe var ve bir işaretçi türü olmayan öğe türüne sahip.  
  
-   Büyüklüğü 8 bayttan fazla olduğundan ve hiçbir işaretçileri içeren bir veri yapısıdır.  
  
-   Kullanarak ayrılan arabellek [_alloca](../../c-runtime-library/reference/alloca.md) işlevi.  
  
-   Bir sınıf veya GS arabellek içeren yapısı.  
  
Örneğin, aşağıdaki deyimleri GS arabellekleri bildirin.  
  
```cpp  
char buffer[20];  
int buffer[20];  
struct { int a; int b; int c; int d; } myStruct;  
struct { int a; char buf[20]; };  
```  
  
Ancak, aşağıdaki deyimleri GS arabellekleri bildirme. İlk iki bildirimleri işaretçi türündeki öğeler içerir. Üçüncü ve dördüncü deyimleri, boyutu çok küçük diziler bildirme. Beşinci ifade bir yapı büyüklüğü platform birden fazla 8 bayt değil bir x86 bildirir.  
  
```cpp  
char *pBuf[20];  
void *pv[20];  
char buf[4];  
int buf[2];  
struct { int a; int b; };  
```  
  
## <a name="initialize-the-security-cookie"></a>Güvenlik tanımlama bilgisi başlatma  
  
**/GS** derleyici seçeneği tanımlama bilgisi kullanan herhangi bir işlev çalıştırmadan önce güvenlik tanımlama bilgisi başlatılması gerekir. Güvenlik tanımlama bilgisi, DLL veya EXE girişindeki hemen başlatılmalıdır. Varsayılan VCRuntime giriş noktaları kullanırsanız, bu otomatik olarak yapılır: mainCRTStartup, wmainCRTStartup, WinMainCRTStartup, wWinMainCRTStartup, veya _DllMainCRTStartup. Bir alternatif giriş noktası kullanıyorsanız, el ile güvenlik tanımlama bilgisi çağırarak başlatmalıdır [__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md).  
  
## <a name="what-is-protected"></a>Ne korumalı  
  
**/GS** derleyici seçeneği aşağıdaki öğeleri korur:  
  
-   İşlev çağrısının dönüş adresi.  
  
-   Bir işlev için bir özel durum işleyici adresi.  
  
-   Güvenlik Açığı işlev parametreleri.  
  
Tüm platformlarda **/GS** arabellek taşmaları dönüş adresi içine algılamaya çalışır. Arabellek aşırı çalıştırmaları daha kolay x86 hem de işlev çağrısının dönüş adresi yığında depolamak çağırma kurallarını kullanmak x64 gibi platformlardaki yararlanan.  
  
Bir işlev bir özel durum işleyici kullanıyorsa x86 üzerinde derleyici özel durum işleyici adresini korumak için güvenlik tanımlama bilgisi ekler. Tanımlama bilgisi, çerçeve geriye doğru izleme sırasında denetlenir.  
  
**/GS** korur *savunmasız parametreleri* bir işlevdeki geçirilir. Bir işaretçi bir C++ başvuru, bir C-bir işaretçi veya GS arabellek içeren yapısı (C++ POD türü) bir güvenlik açığı parametredir.  
  
Bir güvenlik açığı parametresi, yerel değişkenleri ve tanımlama bilgisi önce tahsis edilir. Arabellek Taşması bu parametrelerin üzerine yazabilirsiniz. Ve şu parametreleri kullanan bir işlev kodda bir saldırı işlevi döndürür ve güvenlik denetimi gerçekleştirilir önce neden olabilir. Bu tehlike en aza indirmek için derleyici sırasında işlevi giriş savunmasız parametreleri bir kopyasını oluşturur ve bunları herhangi arabellekleri için depolama alanı altına yerleştirir.  
  
Derleyici savunmasız parametreleri kopyalarını aşağıdaki durumlarda yapmaz:  
  
-   GS arabellek içermeyen işlevleri.  
  
-   En iyi duruma getirme ([/O seçenekler](../../build/reference/o-options-optimize-code.md)) etkin değil.  
  
-   Değişken bağımsız değişken listesi (...) çalışır.  
  
-   İle işaretlenen işlevleri [naked](../../cpp/naked-cpp.md).  
  
-   Satır içi derleme kodunda ilk ifadesinde içeren işlevler.  
  
-   Bir parametre yalnızca bir arabellek taşması durumunda Etkilenme olma olasılığı daha şekilde kullanılır.  
  
## <a name="what-is-not-protected"></a>Ne korunmuyor  
  
**/GS** derleyici seçeneği tüm arabellek taşması güvenlik saldırılarına karşı koruma sağlamaz. Örneğin, bir nesne bir arabellek ve bir vtable varsa, bir arabellek taşması vtable bozuk olabilir.  
  
Kullansanız bile **/GS**, her zaman hiçbir arabellek taşmaları sahip güvenli kod yazmayı deneyin.  
  
### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio'da Bu derleyici seçeneği ayarlamak için  
  
1.  İçinde **Çözüm Gezgini**, projeye sağ tıklayın ve ardından **özellikleri**.  
  
     Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  İçinde **özellik sayfaları** iletişim kutusu, tıklatın **C/C++** klasör.  
  
3.  Tıklatın **kod oluşturma** özellik sayfası.  
  
4.  Değiştirme **arabellek güvenlik denetimi** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BufferSecurityCheck%2A>.  
  
## <a name="example"></a>Örnek  
  
Bu örnek bir arabellek taşar. Bu uygulamanın çalışma zamanında başarısız olmasına neden olur.  
  
```C  
// compile with: /c /W1  
#include <cstring>  
#include <stdlib.h>  
#pragma warning(disable : 4996)   // for strcpy use  
  
// Vulnerable function  
void vulnerable(const char *str) {  
   char buffer[10];  
   strcpy(buffer, str); // overrun buffer !!!  
  
   // use a secure CRT function to help prevent buffer overruns  
   // truncate string to fit a 10 byte buffer  
   // strncpy_s(buffer, _countof(buffer), str, _TRUNCATE);  
}  
  
int main() {  
   // declare buffer that is bigger than expected  
   char large_buffer[] = "This string is longer than 10 characters!!";  
   vulnerable(large_buffer);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
  
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)