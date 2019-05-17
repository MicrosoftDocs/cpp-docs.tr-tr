---
title: /clr Kısıtlamalar
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], restrictions
ms.assetid: 385f6462-2c68-46d6-810e-469553ead447
ms.openlocfilehash: d0318ce2e23f92600d5a78d6472646ec91492152
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837371"
---
# <a name="clr-restrictions"></a>/clr Kısıtlamalar

Kullanımı ile ilgili aşağıdaki kısıtlamalara dikkat edin **/CLR**:

- Yapılandırılmış özel durum işleyici, kullanılmasındaki kısıtlamalar vardır `_alloca` ile derleme yaparken **/CLR**. Daha fazla bilgi için [_alloca](../../c-runtime-library/reference/alloca.md).

- Çalışma zamanı hata denetimleri kullanımı ile geçerli değil **/CLR**. Daha fazla bilgi için [nasıl yapılır: Yerel çalışma zamanı denetimlerini kullanma](/visualstudio/debugger/how-to-use-native-run-time-checks).

- Zaman **/CLR** olduğundan yalnızca standart C++ söz dizimini kullanan bir programı derlemek için kullanılan, satır içi derlemenin kullanılması için aşağıdaki kurallar uygulanır:

  - Yerel yığın düzeni bilgi varsayar satır içi derleme kodu, çağırma kuralları geçerli işlev veya diğer alt düzey bilgisayar bilgileri dışında bilgi yönetilen bir işlev için yığın çerçevesinin uygulanan başarısız olabilir. Satır içi derleme kodu içeren İşlevler, yönetilmeyen işlevleri oluşturulur, sanki olmadan derlendi ayrı bir modül içindeki verildikleri **/CLR**.

  - Satır içi derleme kodu kopyalama oluşturulmuş işlevi parametreleri işlevlerde desteklenmiyor.

- [Vprintf işlevleri](../../c-runtime-library/vprintf-functions.md) ile derlenmiş bir programdan çağrılamaz **/CLR**.

- [Naked](../../cpp/naked-cpp.md) [__declspec](../../cpp/declspec.md) değiştiricisi, / CLR altında yoksayılır.

- Translator işlevi belirlediği [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) yalnızca yönetilmeyen kodda Özek durumları yakalayan etkiler. Bkz: [özel durum işleme](../../extensions/exception-handling-cpp-component-extensions.md) daha fazla bilgi için.

- İşlev işaretçileri karşılaştırma altında izin verilmiyor **/CLR**.

- Tam prototipi oluşturulmuş olmayan işlevlerin kullanımını altında izin verilmiyor **/CLR**.

- Aşağıdaki derleyici seçeneklerinin ile desteklenmez **/CLR**:

  - **/ EHsc** ve **EHS** (**/CLR** gelir **/eha** (bkz [/EH (özel durum işleme modeli)](eh-exception-handling-model.md))

  - **/ FP: katı** ve **/FP: except** (bkz [FP (Floating-Point davranışını belirtin)](fp-specify-floating-point-behavior.md))

  - [/Zd](z7-zi-zi-debug-information-format.md)

  - [/Gm](gm-enable-minimal-rebuild.md)

  - [/MT](md-mt-ld-use-run-time-library.md)

  - [/ RTC](rtc-run-time-error-checks.md)

  - [/ZI](z7-zi-zi-debug-information-format.md)

- Birleşimi `_STATIC_CPPLIB` önişlemci tanımı (`/D_STATIC_CPPLIB`) ve **/CLR** derleyici seçeneği desteklenmiyor. Uygulamanızın statik birden çok iş parçacıklı C++ Standart desteklenmeyen kitaplığı ile bağlantı tanımı neden bunu olmasıdır. Daha fazla bilgi için [/MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](md-mt-ld-use-run-time-library.md) konu.

- Kullanırken **/zi** ile **/CLR**, performans etkileri vardır. Daha fazla bilgi için [/zi](z7-zi-zi-debug-information-format.md).

- Bir geniş karakter için bir .NET Framework geçirme çıkış yordamı da belirtmeden [/ZC: wchar_t](zc-wchar-t-wchar-t-is-native-type.md) veya karakter atama olmadan `__wchar_t` çıkış olarak görünmesi neden olacak bir `unsigned short int`. Örneğin:

    ```cpp
    Console::WriteLine(L' ')              // Will output 32.
    Console::WriteLine((__wchar_t)L' ')   // Will output a space.
    ```

- [/GS](gs-buffer-security-check.md) ile derleme yaparken göz ardı edilir **/CLR**, altında bir işlev olmadığı sürece `#pragma` [yönetilmeyen](../../preprocessor/managed-unmanaged.md) veya işlevi için yerel olarak derlenmelidir ise bu durumda derleyici üretir Varsayılan olarak kapalıdır C4793, uyarı.

- Bkz: [/Entry](entry-entry-point-symbol.md) işlev imzası gereksinimlerini yönetilen bir uygulama için.

- İle derlenmiş uygulamaları **/OpenMP** ve **/CLR** yalnızca tek bir appdomain işleminde çalıştırılabilir.  Bkz: [/OpenMP (OpenMP 2.0 desteğini etkinleştir)](openmp-enable-openmp-2-0-support.md) daha fazla bilgi için.

- Değişken sayıda bağımsız değişkenler (varargs) almayan işlevleri yerel işlevleri oluşturulur. Değişken bağımsız değişken konumu içindeki herhangi bir yönetilen veri türleri için yerel türler sıralanacağını. Unutmayın <xref:System.String?displayProperty=fullName> türleri gerçekten geniş karakterli dizelerdir, ancak tek baytlı karakter dizeleri için hazırlanırlar. Printf belirticisi %S (wchar_t *) ise, bu nedenle, %s dizeye yerine sıralama.

- Va_arg makrosu kullanırken ile derlerken beklenmeyen sonuçlar alabilirsiniz **/CLR: pure**. Daha fazla bilgi için [va_copy, olan va_arg, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 ve sonraki sürümlerde desteklenmiyor. "Saf" veya "güvenli" olmalıdır kod unity'nin için C#.

- Size, yönetilen koddan (işlev bağımsız değişkenleri); parametre bilgilerini almak için stack size yol gösteren tüm işlevleri çağırmalıdır değil P/Invoke katmanı yığın ayırabilir, bu bilgileri neden olur.  Örneğin, proxy/saplama derlenmiyor **/CLR**.

- Yönetilen kod için mümkün olduğunca derlenmiş İşlevler, ancak tüm C++ yapıları yönetilen koda çevrilebilir.  Bu belirleme işlev tarafından işlevi olarak yapılır. Yönetilen kod için işlev herhangi bir bölümünü döndürülemezse tüm işlevi yerine yerel koda dönüştürülür. Aşağıdaki durumlarda derleyici, yönetilen kodu oluşturmasını engeller.

  - Derleyicinin ürettiği dönüştürücüleri veya yardımcı işlevler. Yerel dönüştürücüleri sanal işlev çağrıları dahil olmak üzere bir işlev işaretçisi aracılığıyla herhangi bir işlev çağrısı için oluşturulur.

  - Bu çağrı işlevleri `setjmp` veya `longjmp`.

  - Makine kaynakları doğrudan yönetmek için bazı iç yordamlar kullanan işlevler. Örneğin, kullanımını `__enable` ve `__disable`, `_ReturnAddress` ve `_AddressOfReturnAddress`, veya multimedya yapı içleri yerel kodda tüm sonuç olur.

  - Bu izleme işlevleri `#pragma unmanaged` yönergesi. (Unutmayın ters `#pragma managed`, ayrıca desteklenir.)

  - Başvurular içeren bir işlev hizalanmış türler, diğer bir deyişle, türleri kullanılarak bildirilen `__declspec(align(...))`.

## <a name="see-also"></a>Ayrıca bkz.

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](clr-common-language-runtime-compilation.md)
