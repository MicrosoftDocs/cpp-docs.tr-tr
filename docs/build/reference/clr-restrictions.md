---
description: Daha fazla bilgi edinin:/clr kısıtlamaları
title: /clr Kısıtlamalar
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], restrictions
ms.assetid: 385f6462-2c68-46d6-810e-469553ead447
ms.openlocfilehash: eb74aea8f1d6fcae4738f17f5fae2a4761350341
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193012"
---
# <a name="clr-restrictions"></a>/clr Kısıtlamalar

**/Clr** kullanımı ile ilgili aşağıdaki kısıtlamalara göz önünde edin:

- Yapılandırılmış bir özel durum işleyicisinde, `_alloca` **/clr** ile derlerken kullanılan kısıtlamalar vardır. Daha fazla bilgi için bkz. [_alloca](../../c-runtime-library/reference/alloca.md).

- Çalışma zamanı hata denetimlerinin kullanımı **/clr** ile geçerli değildir. Daha fazla bilgi için bkz. [nasıl yapılır: yerel Run-Time denetimleri kullanma](/visualstudio/debugger/how-to-use-native-run-time-checks).

- **/Clr** yalnızca standart C++ söz dizimini kullanan bir programı derlemek için kullanıldığında, satır içi derlemenin kullanımı için aşağıdaki yönergeler geçerlidir:

  - Yerel yığın düzeni hakkında bilgi sahibi olan satır içi derleme kodu, geçerli işlevin dışındaki kuralları çağırma veya yönetilen bir işlev için yığın çerçevesine bu bilgi uygulanırsa bilgisayar hakkındaki diğer alt düzey bilgiler başarısız olabilir. Satır içi derleme kodu içeren işlevler, **/clr** olmadan derlenen ayrı bir modüle yerleştirilmiş gibi yönetilmeyen işlevler olarak oluşturulur.

  - Kopyalama ile oluşturulmuş işlev parametrelerini geçiren işlevlerde satır içi derleme kodu desteklenmiyor.

- [Vprintf işlevleri](../../c-runtime-library/vprintf-functions.md) **/clr** ile derlenen bir programdan çağrılamaz.

- [Naked](../../cpp/naked-cpp.md) [__declspec](../../cpp/declspec.md) değiştiricisi/CLRaltında yok sayılır.

- [_Set_se_translator](../../c-runtime-library/reference/set-se-translator.md) tarafından ayarlanan Translator işlevi yalnızca yönetilmeyen koddaki catch 'i etkiler. Daha fazla bilgi için bkz. [özel durum işleme](../../extensions/exception-handling-cpp-component-extensions.md) .

- İşlev işaretçilerinin karşılaştırmasına **/clr** altında izin verilmez.

- Tam prototipi bulunmayan işlevlerin kullanılmasına **/clr** altında izin verilmez.

- Aşağıdaki derleyici seçenekleri **/clr** ile desteklenmez:

  - **/EHsc** ve **/EHS** (**/clr** , **/EHa** gerektirir (bkz. [/Eh (özel durum işleme modeli)](eh-exception-handling-model.md))

  - **/FP: Strict** ve **/FP: except** (bkz. [/FP (Floating-Point davranışını belirt)](fp-specify-floating-point-behavior.md))

  - [/ZD](z7-zi-zi-debug-information-format.md)

  - [/GM](gm-enable-minimal-rebuild.md)

  - [/MT](md-mt-ld-use-run-time-library.md)

  - [/RTC](rtc-run-time-error-checks.md)

  - [/ZI](z7-zi-zi-debug-information-format.md)

- `_STATIC_CPPLIB`Önişlemci tanımının ( `/D_STATIC_CPPLIB` ) ve **/clr** derleyici seçeneğinin birleşimi desteklenmez. Bu, tanım uygulamanızın statik çok iş parçacıklı C++ standart kitaplığıyla bağlantı oluşturmasına neden olacağından, desteklenmeyen bir uygulamadır. Daha fazla bilgi için bkz. [/MD,/MT,/LD (Run-Time kitaplığı kullanın)](md-mt-ld-use-run-time-library.md) konusu.

- **/Clr** ile **/Zi** kullanırken performans olumsuz etkileri vardır. Daha fazla bilgi için bkz. [/Zi](z7-zi-zi-debug-information-format.md).

- Bir .NET Framework çıkış yordamına, [/Zc: wchar_t](zc-wchar-t-wchar-t-is-native-type.md) veya karakteri atama olmadan geniş bir karakter geçirme, **`__wchar_t`** çıktının bir olarak görünmesine neden olur `unsigned short int` . Örneğin:

    ```cpp
    Console::WriteLine(L' ')              // Will output 32.
    Console::WriteLine((__wchar_t)L' ')   // Will output a space.
    ```

- Bir işlev yönetilmeyen olarak veya işlevin yerel olarak derlenmesi gerekiyorsa, **/clr** ile derlerken [/GS](gs-buffer-security-check.md) yok sayılır `#pragma` [](../../preprocessor/managed-unmanaged.md) . Bu durumda, derleyici varsayılan olarak kapalı olan uyarı C4793 oluşturur.

- Yönetilen bir uygulamanın işlev imzası gereksinimleri için bkz. [/Entry](entry-entry-point-symbol.md) .

- **/OpenMP** ve **/clr** ile derlenen uygulamalar yalnızca tek bir AppDomain işleminde çalıştırılabilir.  Daha fazla bilgi için bkz. [/OpenMP (openmp 2,0 desteğini etkinleştir)](openmp-enable-openmp-2-0-support.md) .

- Değişken sayıda bağımsız değişken (varargs) alan işlevler, yerel işlevler olarak oluşturulur. Değişken bağımsız değişkeni konumundaki yönetilen tüm veri türleri yerel türlere göre sıralanır. <xref:System.String?displayProperty=fullName>Türlerin gerçekten geniş karakterli dizeler olduğunu, ancak tek baytlık karakter dizelerine sıralandığına unutmayın. Bu nedenle, bir printf belirticisi% S (wchar_t *) ise, bunun yerine% s dizesine göre sıralama yapılır.

- Va_arg makrosunu kullanırken, **/clr: Pure** ile derlerken beklenmedik sonuçlar alabilirsiniz. Daha fazla bilgi için bkz. [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md). **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ve sonrasında desteklenmez. "Saf" veya "güvenli" olması gereken kod C# ' ye eklenmelidir.

- Yönetilen koddan, yığın üzerinde parametre bilgilerini almak için yol gösteren işlevlerden (işlev bağımsız değişkenleri) çağrı yapmanız gerekmez; P/Invoke katmanı, bu bilgilerin yığının daha ileri altına alınmasına neden olur.  Örneğin, **/clr** ile proxy/saplama derlenemiyor.

- İşlevler mümkün olduğunda yönetilen koda derlenir, ancak tüm C++ yapıları yönetilen koda çevrilemeyebilir.  Bu belirleme işlevi işlev temelinde yapılır. Bir işlevin herhangi bir bölümü yönetilen koda dönüştürülemiyorsa, tüm işlev bunun yerine yerel koda dönüştürülür. Aşağıdaki durumlar derleyicinin yönetilen kod oluşturmasını engeller.

  - Derleyicinin ürettiği dönüştürücüler veya yardımcı işlevleri. Yerel dönüştürücüler, sanal işlev çağrıları dahil olmak üzere bir işlev işaretçisi aracılığıyla herhangi bir işlev çağrısı için oluşturulur.

  - Veya çağıran işlevler `setjmp` `longjmp` .

  - Makine kaynaklarını doğrudan işlemek için belirli iç yordamları kullanan işlevler. Örneğin, `__enable` ve, `__disable` `_ReturnAddress` , ya da multimedya iç bilgileri kullanımı, `_AddressOfReturnAddress` yerel koda neden olur.

  - Yönergesini izleyen işlevler `#pragma unmanaged` . (Ters, `#pragma managed` ,, ayrıca desteklenir.)

  - Hizalanmış türlere yönelik başvuruları, yani kullanılarak belirtilen türleri içeren bir işlev `__declspec(align(...))` .

## <a name="see-also"></a>Ayrıca bkz.

- [/clr (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md)
