---
description: Daha fazla bilgi edinin:/GS (arabellek güvenlik denetimi)
title: /GS (Arabellek Güvenlik Denetimi)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BufferSecurityCheck
- VC.Project.VCCLCompilerTool.BufferSecurityCheck
helpviewer_keywords:
- buffers [C++], buffer overruns
- buffer overruns, compiler /GS switch
- GS compiler option [C++]
- /GS compiler option [C++]
- security check compiler option [C++]
- -GS compiler option [C++]
- buffers [C++], avoiding overruns
ms.assetid: 8d8a5ea1-cd5e-42e1-bc36-66e1cd7e731e
ms.openlocfilehash: 4d7fa3c2220260914c9ff931c2f2e7c76bf12ea1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191881"
---
# <a name="gs-buffer-security-check"></a>/GS (Arabellek Güvenlik Denetimi)

Bir işlevin dönüş adresini, özel durum işleyicisi adresini veya belirli parametre türlerini geçersiz kılacak bazı arabellek taşmalarını algılar. Arabellek taşmasına neden olan saldırganlar, arabellek boyutu kısıtlamalarını zorlayamayan kodun yararlanabilmesi için kullanılan bir tekniktir.

## <a name="syntax"></a>Syntax

```
/GS[-]
```

## <a name="remarks"></a>Açıklamalar

**/GS** varsayılan olarak açık olur. Uygulamanızda güvenlik pozlaması olmasını bekleliyorsanız, **/GS-** kullanın. Arabellek taşması algılamayı gizleme hakkında daha fazla bilgi için bkz. [safebuffers](../../cpp/safebuffers.md).

## <a name="security-checks"></a>Güvenlik denetimleri

Derleyicinin, arabellek taşma sorunlarına bağlı olarak tanıdığı işlevlerde, derleyici dönüş adresinden önce yığın üzerinde alan ayırır. İşlev girişinde, ayrılan alan, modül yüklenirken bir kez hesaplanan bir *güvenlik tanımlama bilgisiyle* yüklenir. İşlev çıkışında ve 64 bit işletim sistemlerinde çerçeve geri sarma sırasında, tanımlama bilgisinin değerinin hala aynı olduğundan emin olmak için bir yardımcı işlev çağırılır. Farklı bir değer, yığının bir üzerine yazma oluşmuş olabilir. Farklı bir değer algılanırsa, işlem sonlandırılır.

## <a name="gs-buffers"></a>GS arabellekleri

Bir ara *arabellekte* arabellek taşması güvenlik denetimi yapılır. GS arabelleği aşağıdakilerden biri olabilir:

- 4 bayttan büyük bir dizi, ikiden fazla öğe içeriyor ve işaretçi türü olmayan bir öğe türüne sahip.

- Boyutu 8 bayttan büyük olan ve işaretçi içermeyen bir veri yapısı.

- [_Alloca](../../c-runtime-library/reference/alloca.md) işlevi kullanılarak ayrılan bir arabellek.

- GS arabelleği içeren herhangi bir sınıf veya yapı.

Örneğin, aşağıdaki deyimler GS arabellekleri bildirir.

```cpp
char buffer[20];
int buffer[20];
struct { int a; int b; int c; int d; } myStruct;
struct { int a; char buf[20]; };
```

Ancak, aşağıdaki deyimler GS arabellekleri bildirmiyor. İlk iki bildirim işaretçi türündeki öğeleri içerir. Üçüncü ve dördüncü deyimler boyutu çok küçük olan dizileri bildirir. Beşinci ifade, bir x86 platformunda boyutu 8 bayttan fazla olmayan bir yapı bildirir.

```cpp
char *pBuf[20];
void *pv[20];
char buf[4];
int buf[2];
struct { int a; int b; };
```

## <a name="initialize-the-security-cookie"></a>Güvenlik tanımlama bilgisini başlatma

**/GS** derleyici seçeneği, tanımlama bilgisini kullanan herhangi bir işlev çalıştırılmadan önce güvenlik tanımlama bilgisinin başlatılmasını gerektirir. Güvenlik tanımlama bilgisinin bir EXE veya DLL girişi üzerinde hemen başlatılması gerekir. Varsayılan VCRuntime giriş noktalarını kullanırsanız, bu otomatik olarak yapılır: mainCRTStartup, wmainCRTStartup, WinMainCRTStartup, wWinMainCRTStartup veya _DllMainCRTStartup. Alternatif bir giriş noktası kullanırsanız, [__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md)çağırarak güvenlik tanımlama bilgisini el ile başlatmalısınız.

## <a name="what-is-protected"></a>Nelerin korunduğu

**/GS** derleyici seçeneği aşağıdaki öğeleri korur:

- İşlev çağrısının dönüş adresi.

- Bir işlev için özel durum işleyicisinin adresi.

- Savunmasız işlev parametreleri.

Tüm platformlarda **/GS** , dönüş adresine arabellek taşmalarını algılamaya çalışır. Arabellek taşmaları, yığın üzerinde bir işlev çağrısının dönüş adresini depolayan çağırma kurallarını kullanan x86 ve x64 gibi platformlarda daha kolay bir şekilde yararlanabilir.

X86 'da, bir işlev bir özel durum işleyicisi kullanıyorsa, derleyici özel durum işleyicisinin adresini korumak için bir güvenlik tanımlama bilgisi çıkarır. Tanımlama bilgisi çerçeve geri sarma sırasında denetlenir.

**/GS** bir işleve geçirilen *savunmasız parametreleri* korur. Savunmasız bir parametre bir işaretçi, C++ başvurusu, bir işaretçi veya bir GS arabelleği içeren C yapısı (C++ POD türü).

Bir güvenlik açığı parametresi, tanımlama bilgisi ve yerel değişkenlerden önce ayrılır. Bir arabellek taşması bu parametrelerin üzerine yazabilir. Ve bu parametreleri kullanan işlevdeki kod, işlev döndürülmadan ve güvenlik denetimi gerçekleştirilmeden önce bir saldırıya neden olabilir. Bu tehlike düzeyini en aza indirmek için, derleyici işlev girişi sırasında güvenlik açığı bulunan parametrelerin bir kopyasını yapar ve bunları herhangi bir arabellek için depolama alanının altına koyar.

Derleyici, aşağıdaki durumlarda güvenlik açığı bulunan parametrelerin kopyalarını yapmaz:

- GS arabelleği içermeyen işlevler.

- İyileştirmeler ([/o seçenekler](o-options-optimize-code.md)) etkin değil.

- Değişken bağımsız değişken listesi (...) olan işlevler.

- [Naked](../../cpp/naked-cpp.md)ile işaretlenen işlevler.

- İlk ifadede satır içi derleme kodu içeren işlevler.

- Bir parametre yalnızca arabellek taşması durumunda açıktan etkilenme olasılığı düşük olan yollarla kullanılır.

## <a name="what-is-not-protected"></a>Korunmuyor

**/GS** derleyici seçeneği, tüm arabellek taşması güvenlik saldırılarına karşı koruma sağlamaz. Örneğin, bir nesnede bir arabellekle ve bir vtable varsa, bir arabellek taşması vtable 'ı bozabilir.

**/GS** kullanıyor olsanız bile, her zaman arabellek taşması olmayan güvenli kod yazmayı deneyin.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio 'da Bu derleyici seçeneğini ayarlamak için

1. **Çözüm Gezgini**, projeye sağ tıklayın ve ardından **Özellikler**' e tıklayın.

   Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Özellik sayfaları** iletişim kutusunda **C/C++** klasörünü tıklatın.

1. **Kod oluşturma** Özellik sayfasına tıklayın.

1. **Arabellek güvenliği denetimi** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BufferSecurityCheck%2A>.

## <a name="example"></a>Örnek

Bu örnek bir arabelleğin taşmalarına sahiptir. Bu, uygulamanın çalışma zamanında başarısız olmasına neden olur.

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

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
