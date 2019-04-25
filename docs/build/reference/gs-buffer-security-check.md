---
title: /GS (Arabellek Güvenlik Denetimi)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BufferSecurityCheck
- VC.Project.VCCLCompilerTool.BufferSecurityCheck
- /GS
helpviewer_keywords:
- buffers [C++], buffer overruns
- buffer overruns, compiler /GS switch
- GS compiler option [C++]
- /GS compiler option [C++]
- security check compiler option [C++]
- -GS compiler option [C++]
- buffers [C++], avoiding overruns
ms.assetid: 8d8a5ea1-cd5e-42e1-bc36-66e1cd7e731e
ms.openlocfilehash: 10afa874092eb563903ba5f49c6add136afc869c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292178"
---
# <a name="gs-buffer-security-check"></a>/GS (Arabellek Güvenlik Denetimi)

Bir işlevin dönüş adresi, özel durum işleyicisi adresini veya belirli bir türdeki parametreleri üzerine bazı arabellek taşmalarına algılar. Arabellek taşmasına neden, arabellek boyutu kısıtlamaları zorunlu kılmaz kod yararlanmak için saldırganlar tarafından kullanılan bir tekniktir.

## <a name="syntax"></a>Sözdizimi

```
/GS[-]
```

## <a name="remarks"></a>Açıklamalar

**/GS** varsayılan olarak açıktır. Uygulamanızın güvenlik gerçekleşmediğinden olmasını beklediğiniz kullanırsanız **/GS-**. Arabellek Taşması algılama gizleme hakkında daha fazla bilgi için bkz. [safebuffers](../../cpp/safebuffers.md).

## <a name="security-checks"></a>Güvenlik denetimleri

Arabellek taşması sorunları gibi tabi derleyici tanır İşlevler, derleyici dönüş adresi önce yığında alan ayırır. İşlev girişte ayrılan alanı ile yüklenen bir *güvenlik tanımlama bilgisi* , hesaplanır kez modülü yük. İşlevi Çıkışta ve 64-bit işletim sistemlerinde çerçeveyi geriye doğru izleme sırasında tanımlama bilgisinin değeri hala aynı olduğundan emin olmak için bir yardımcı işlev çağrılır. Yığın üzerine oluşmuş olabilir, farklı bir değer belirtir. Farklı bir değer algılanırsa, işlem sonlandırıldı.

## <a name="gs-buffers"></a>GS arabellekler

Arabellek Güvenlik denetimi gerçekleştirilir bir *GS arabellek*. GS arabellek bunlardan biri olabilir:

- 4 bayt değerinden daha büyük bir dizi ikiden fazla öğe varsa ve bir öğe türüne bir işaretçi türü değil.

- Boyutu 8 bayttan fazla olması ve hiçbir işaretçiler içeren veri yapısı.

- Kullanarak ayrılan bir arabellek [_alloca](../../c-runtime-library/reference/alloca.md) işlevi.

- Bir sınıf veya GS arabellek içeren yapısı.

Örneğin, aşağıdaki deyimleri GS arabellekler bildirin.

```cpp
char buffer[20];
int buffer[20];
struct { int a; int b; int c; int d; } myStruct;
struct { int a; char buf[20]; };
```

Ancak, aşağıdaki deyimleri GS arabellekler bildirmeyin. İlk iki bildirimleri işaretçi türünde öğeler içerir. Üçüncü ve dördüncü deyimler dizi boyutu çok küçükse bildirin. Beşinci ifade bir yapı platformu birden fazla 8 bayt değil bir x86 üzerinde boyutu bildirir.

```cpp
char *pBuf[20];
void *pv[20];
char buf[4];
int buf[2];
struct { int a; int b; };
```

## <a name="initialize-the-security-cookie"></a>Güvenlik tanımlama bilgisi Başlat

**/GS** derleyici seçeneği güvenlik tanımlama bilgisi tanımlama bilgisini kullanan herhangi bir işlev çalıştırılmadan önce başlatılması gerekir. Güvenlik tanımlama bilgisi, bir EXE veya DLL Giriş hemen başlatılmalıdır. Varsayılan VCRuntime giriş noktalarını kullanırsanız, bu otomatik olarak gerçekleştirilir: mainCRTStartup, wmainCRTStartup, WinMainCRTStartup, wWinMainCRTStartup, veya _DllMainCRTStartup. Alternatif bir giriş noktası kullanıyorsanız, el ile güvenlik tanımlama bilgisi çağırarak başlatmalıdır [__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md).

## <a name="what-is-protected"></a>Neler korunuyor

**/GS** derleyici seçeneği, aşağıdaki öğeleri korur:

- Bir işlev çağrısının dönüş adresi.

- Özel durum işleyicisi bir işlevin adresi.

- Güvenlik Açığı işlev parametreleri.

Tüm platformlarda **/GS** dönüş adresi içine arabellek taşmalarını algılamaya çalışır. Arabellek taşmaları, daha kolay x86 ve bir işlev çağrısının dönüş adresi yığında depolamak çağırma kurallarını kullanan x64 gibi platformlarda doğmasına.

Bir işlev bir özel durum işleyicisi kullanıyorsa x86 üzerinde derleyici özel durum işleyicisi adresini korumak için güvenlik tanımlama bilgisi ekler. Tanımlama bilgisi çerçeveyi geriye doğru izleme sırasında denetlenir.

**/GS** korur *savunmasız parametreleri* işleve geçirildi. Bir C-bir işaretçi veya GS arabellek içeren yapısı (C++ POD türü) bir C++ başvurusu bir işaretçi bir güvenlik açığı parametredir.

Güvenlik açığı bulunan bir parametre, yerel değişkenleri ve tanımlama bilgisi önce ayrılır. Bu parametreleri bir arabellek taşması üzerine yazabilirsiniz. Ve bu parametreleri kullanan bir işlev kodu bir saldırı işlevi döndürür ve güvenlik denetimi gerçekleştirilir önce neden olabilir. Bu tehlike en aza indirmek için derleyici işlev girişi sırasında savunmasız parametreleri kopyasını oluşturur ve bunları tüm arabellekler için depolama alanı aşağıda koyar.

Derleyici, aşağıdaki durumlarda savunmasız parametreleri kopyalarını yapmaz:

- GS arabellek içermeyen işlevleri.

- En iyi duruma getirme ([/O seçenekler](o-options-optimize-code.md)) etkin değil.

- Değişken bağımsız değişken listesi (...) işlevleri.

- İle işaretlenen işlevler [naked](../../cpp/naked-cpp.md).

- İlk deyim içinde satır içi derleme kodu içeren işlevler.

- Bir parametresi olan bir arabellek taşması durumunda açıklardan olma olasılığı daha yollarını kullanılır.

## <a name="what-is-not-protected"></a>Hangi korumalı değil

**/GS** derleyici seçeneği tüm arabellek taşması güvenlik saldırılarına karşı koruma sağlamaz. Örneğin, bir nesnenin bir arabellek ve bir vtable varsa, bir arabellek taşması vtable bozuk olabilir.

Kullansanız bile **/GS**, hiçbir arabellek taşmalarına sahip güvenli kod yazmak her zaman deneyin.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Bu derleyici seçeneğini Visual Studio'da ayarlamak için

1. İçinde **Çözüm Gezgini**, projeye sağ tıklayın ve ardından **özellikleri**.

   Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. İçinde **özellik sayfaları** iletişim kutusu, tıklayın **C/C++** klasör.

1. Tıklayın **kod oluşturma** özellik sayfası.

1. Değiştirme **arabellek güvenlik denetimi** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BufferSecurityCheck%2A>.

## <a name="example"></a>Örnek

Bu örnek, bir arabellek taşmasına neden. Bu, uygulamanın çalışma zamanında başarısız olmasına neden olur.

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

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
