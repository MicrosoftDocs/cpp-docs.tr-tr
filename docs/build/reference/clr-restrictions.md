---
title: / CLR kısıtlamalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /clr compiler option [C++], restrictions
ms.assetid: 385f6462-2c68-46d6-810e-469553ead447
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34d21939f51fc3d4800d5cdd887b283b7e690db6
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704275"
---
# <a name="clr-restrictions"></a>/clr Kısıtlamalar

Kullanımı ile ilgili aşağıdaki kısıtlamalar Not **/CLR**:

- Yapılandırılmış özel durum işleyici, kullanılmasındaki kısıtlamalar vardır `_alloca` ile derleme yapılırken **/CLR**. Daha fazla bilgi için bkz: [_alloca](../../c-runtime-library/reference/alloca.md).

- Çalışma zamanı hata denetimleri kullanımı geçerli değil **/CLR**. Daha fazla bilgi için bkz: [nasıl yapılır: çalışma zamanı kullanmak yerel denetler](/visualstudio/debugger/how-to-use-native-run-time-checks).

- Zaman **/CLR** olduğundan yalnızca standart C++ söz dizimini kullanan bir program derlemek için kullanılan, satır içi derleme kullanmak için aşağıdaki yönergeleri uygulayın:

  - Yerel yığın düzeni bilgisi varsayan satır içi derleme kodu çağırma kuralları geçerli işlevi veya bilgisayarla ilgili diğer alt düzey bilgiler dışında bilgi yönetilen bir işlev için yığın çerçevesi uygulanan başarısız olabilir. Satır içi derleme kodu içeren işlevleri, yönetilmeyen işlevler oluşturulur, olmadan derlenen ayrı bir modül olarak yerleştirildi sanki **/CLR**.

  - Satır içi derleme kodunda kopyalama oluşturulan işlev parametreleri işlevleri desteklenmez.

- [Vprintf işlevleri](../../c-runtime-library/vprintf-functions.md) ile derlenen bir programdan çağrılamaz **/CLR**.

- [Naked](../../cpp/naked-cpp.md) [__declspec](../../cpp/declspec.md) değiştiricisi/CLR altında göz ardı edilir.

- Set Çeviricisi işlevi [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) yalnızca önbellek yönetilmeyen kodunda etkiler. Bkz: [özel durum işleme](../../windows/exception-handling-cpp-component-extensions.md) daha fazla bilgi için.

- İşlev işaretçileri karşılaştırma altında izin verilmiyor **/CLR**.

- Tam olarak örneklenmiş olmayan işlevleri kullanımını altında izin verilmiyor **/CLR**.

- Aşağıdaki derleyici seçenekleri ile desteklenmez **/CLR**:

  - **/ EHsc** ve **/EHs** (**/CLR** gelir **/EHa** (bkz [/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md))

  - **/FP: katı** ve **/fp: dışında** (bkz [/fp (Floating-Point davranış belirtin)](../../build/reference/fp-specify-floating-point-behavior.md))

  - [/Zd](../../build/reference/z7-zi-zi-debug-information-format.md)

  - [/Gm](../../build/reference/gm-enable-minimal-rebuild.md)

  - [/MT](../../build/reference/md-mt-ld-use-run-time-library.md)

  - [/ RTC](../../build/reference/rtc-run-time-error-checks.md)

  - [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)

- Birleşimi `_STATIC_CPPLIB` önişlemci tanımı (`/D_STATIC_CPPLIB`) ve **/CLR** derleyici seçeneği desteklenmez. Tanımı statik birden çok iş parçacıklı C++ Standart desteklenmeyen kitaplığı ile bağlantı için uygulamanızı neden olacağından bunu olmasıdır. Daha fazla bilgi için bkz: [/MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md) konu.

- Kullanırken **/zı** ile **/CLR**, performans etkileri vardır. Daha fazla bilgi için bkz: [/zı](../../build/reference/z7-zi-zi-debug-information-format.md).

- .NET Framework için geniş karakter geçirme çıktı yordamı da belirtilmeden [/ZC: wchar_t](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) veya karakter atama olmadan `__wchar_t` olarak görünmesi çıktı neden olacak bir `unsigned short int`. Örneğin:

    ```cpp
    Console::WriteLine(L' ')              // Will output 32.
    Console::WriteLine((__wchar_t)L' ')   // Will output a space.
    ```

- [/GS](../../build/reference/gs-buffer-security-check.md) ile derleme yapılırken dikkate **/CLR**, altında bir işlev olmadığı sürece `#pragma` [yönetilmeyen](../../preprocessor/managed-unmanaged.md) veya işlevi için yerel olarak derlenmelidir varsa, bu durumda derleyici üretir Varsayılan olarak kapalıdır C4793 uyarı.

- Bkz: [/Entry](../../build/reference/entry-entry-point-symbol.md) yönetilen bir uygulamanın işlevi imza gereksinimlerini için.

- Uygulamaları derlenmiş ile **/OpenMP** ve **/CLR** yalnızca bir tek appdomain işlemde çalıştırılabilir.  Bkz: [/OpenMP (OpenMP 2.0 desteğini etkinleştir)](../../build/reference/openmp-enable-openmp-2-0-support.md) daha fazla bilgi için.

- Değişken sayıda bağımsız değişkenler (varargs) almayan işlevleri yerel işlevler oluşturulur. Değişken bağımsız değişken konumda herhangi bir yönetilen veri türleri için yerel türleri başvuruya. Unutmayın <xref:System.String?displayProperty=fullName> türleridir gerçekte joker karakter dizeleri, ancak tek baytlı karakter dizeleri hazırlanırlar. Printf belirleyici %S (wchar_t *) ise, bu nedenle, %s dizeye yerine sıralama.

- Va_arg makrosu kullanırken ile derleme yapılırken beklenmeyen sonuçlar alabilirsiniz **/CLR: pure**. Daha fazla bilgi için bkz: [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor. "Saf" veya "safe" olmalıdır kod C# için bağlantı noktası kurulmuş.

- Yönetilen koddan parametre bilgilerini (işlev bağımsız değişkenleri); almak için yığın yol işlevleri çağırmalısınız değil P/Invoke katman yığın başka olması bu bilgileri neden olur.  Örneğin, proxy/stub ile derleme değil **/CLR**.

- Yönetilen kod için mümkün olduğunca derlenmiş İşlevler, ancak tüm C++ yapıları yönetilen koda çevrilebilir.  Bu belirleme, bir işlev tarafından işlevi temelinde yapılır. Yönetilen kod için işlev herhangi bir kısmını dönüştürülemiyorsa tüm işlevi yerel koda yerine dönüştürülür. Aşağıdaki durumlarda, yönetilen kod oluşturma derleyici engeller.

  - Derleyicinin ürettiği dönüştürücüler veya yardımcı işlevleri. Yerel dönüştürücüler sanal işlev çağrıları dahil olmak üzere bir işlev işaretçisi aracılığıyla herhangi bir işlev çağrısı için oluşturulur.

  - Bu çağrı işlevleri `setjmp` veya `longjmp`.

  - İşlevler doğrudan makine kaynakları yönetmek için belirli iç yordamları kullanın. Örneğin, kullanımını `__enable` ve `__disable`, `_ReturnAddress` ve `_AddressOfReturnAddress`, veya multimedya iç bilgileri yerel kod tüm sonuçlanır.

  - Bu izleme işlevleri `#pragma unmanaged` yönergesi. (Unutmayın ters `#pragma managed`, ayrıca desteklenir.)

  - Başvuruları içeren bir işlev hizalı türleri, diğer bir deyişle, türleri kullanılarak bildirilen `__declspec(align(...))`.

## <a name="see-also"></a>Ayrıca bkz.

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)
