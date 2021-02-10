---
title: C++ belgeleri için yenilikler
description: Microsoft C/C++ derleyicisi, ATL/MFC, C çalışma zamanı ve standart kitaplık belgeleri için yeni belgeler ve belge güncelleştirmeleri.
ms.date: 02/08/2021
ms.openlocfilehash: 3b6d248b99415c91b4086b00ecc54fc39d2c348a
ms.sourcegitcommit: 77235bff6a7b2621c501938e30d93cb15f5733cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2021
ms.locfileid: "100006038"
---
# <a name="microsoft-c-docs-whats-new-for-visual-studio-168"></a>Microsoft C++ belgeleri: Visual Studio 16,8 yenilikleri

Bu makalede, Visual Studio 16,8 için docs 'a yönelik önemli değişikliklerden bazıları listelenir. 

Visual Studio 'daki yenilikler hakkında daha fazla bilgi için bkz. [Visual Studio 'Da C++](what-s-new-for-visual-cpp-in-visual-studio.md)yenilikleri.

En son C++ uygunluk durumu için bkz. [Visual Studio 'da C++ uygunluk iyileştirmeleri](cpp-conformance-improvements.md)

## <a name="c-language"></a>C dili

### <a name="new-articles"></a>Yeni makaleler

- [`_Noreturn` anahtar sözcük ve `noreturn` makro (C11)](../c-language/noreturn.md)
- [_Static_assert anahtar sözcüğü ve static_assert makrosu (C11)](../c-language/static-assert-c.md)

### <a name="updated-articles"></a>Güncelleştirilmiş makaleler

- [C Command-Line bağımsız değişkenlerini ayrıştırma](../c-language/parsing-c-command-line-arguments.md) -c bağımsız değişkenlerini ayrıştırmak için kurallara belge özel durumları
- [Tür niteleyicileri](../c-language/type-qualifiers.md) -eklendi `restrict`
- [C atama işleçleri](../c-language/c-assignment-operators.md) -C17 için sözcük dilbilgisi güncelleştirmesi
- [C anahtar sözcükleri](../c-language/c-keywords.md) -C17 için sözlü dil güncelleştirmesi
- [C sözcük temelli dilbilgisi](../c-language/lexical-grammar.md) -C17 için sözlü dil güncelleştirmesi
- [Bildirimlerin Özeti](../c-language/summary-of-declarations.md) -C17 için sözcük dilbilgisi güncelleştirmesi
- [Ifadelerin Özeti](../c-language/summary-of-expressions.md) -C17 için sözlü dil güncelleştirmesi
- [C numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md) -sabit sözcük dilbilgisi
- [C deyimlerinin Özeti](../c-language/summary-of-statements.md) -için güncelleştirilmiş `__leave` , `__try` anahtar sözcükler

## <a name="c-runtime-library"></a>C çalışma zamanı kütüphanesi

### <a name="new-articles"></a>Yeni makaleler

- [Türe özel matematik](../c-runtime-library/tgmath.md)

### <a name="updated-articles"></a>Güncelleştirilmiş makaleler

- [`qsort`](../c-runtime-library/reference/qsort.md) -Kararlılık hakkında Note eklendi
- [`_cwait`](../c-runtime-library/reference/cwait.md) -Fixed Code örneği
- [İşlev ailesine genel bakış](../c-runtime-library/function-family-overviews.md) -eklenen işleç `new` ve `delete`
- [`round, roundf, roundl`](../c-runtime-library/reference/round-roundf-roundl.md) -Açıklığa kavuşturuldu yuvarlama kodu örneği
- [Uyumluluk](../c-runtime-library/compatibility.md) -eklenen C99 uygunluk notları
- [`realloc`](../c-runtime-library/reference/realloc.md) -C99 uygunluk notları eklendi
- [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md) -C99 uygunluk notları eklendi
- [`assert Macro, _assert, _wassert`](../c-runtime-library/reference/assert-macro-assert-wassert.md) -Açıklanan onaylama davranışı
- [`vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l`](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md) -Açıklanan dönüş değerleri
- [`setlocale, _wsetlocale`](../c-runtime-library/reference/setlocale-wsetlocale.md) -C çalışma zamanı UTF-8 destek bilgisi eklendi

## <a name="cc-preprocessor-reference"></a>C/C++ ön işlemci başvurusu

### <a name="updated-articles"></a>Güncelleştirilmiş makaleler

- [Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md) -16,8 sürüm notlarına güncelleştirildi, C11/C17 `/std` desteği ve SDK docs Install
- [MSVC yeni Önişlemci genel bakış](../preprocessor/preprocessor-experimental-overview.md) -güncelleştirilmiş Önişlemci içeriği

## <a name="code-quality"></a>Kod kalitesi

### <a name="new-articles"></a>Yeni makaleler

- [C33001](../code-quality/c33001.md) -VC kod analizi-16,8 sürümündeki yeni kurallar için ekleme
- [C33004](../code-quality/c33004.md) -VC kod analizi-16,8 sürümündeki yeni kurallar için ekleme
- [C33005](../code-quality/c33005.md) -VC kod analizi-16,8 sürümündeki yeni kurallar için ekleme
- [C33010](../code-quality/c33010.md) -VC kod analizi-16,8 sürümündeki yeni kurallar için ekleme
- [C33011](../code-quality/c33011.md) -VC kod analizi-16,8 sürümündeki yeni kurallar için ekleme
- [C33020](../code-quality/c33020.md) -VC kod analizi-16,8 sürümündeki yeni kurallar için ekleme
- [C33022](../code-quality/c33022.md) -VC kod analizi-16,8 sürümündeki yeni kurallar için ekleme

### <a name="updated-articles"></a>Güncelleştirilmiş makaleler

- [`C6262`](../code-quality/c6262.md) -Address cpp-docs. zh-TW sorun 20
- [`C26497 USE_CONSTEXPR_FOR_FUNCTION`](../code-quality/c26497.md) -C26497 'e örnek eklendi
- [`C26496 USE_CONST_FOR_VARIABLE`](../code-quality/c26496.md) -C26496 'e örnek eklendi
- [`C26495 MEMBER_UNINIT`](../code-quality/c26495.md) -C26495 ' deki güncelleştirilmiş örnekler ve bağlantılar
- [`C26483 STATIC_INDEX_OUT_OF_RANGE`](../code-quality/c26483.md) -C26483 'e örnek eklendi
- [`C26462 USE_CONST_POINTER_FOR_VARIABLE`](../code-quality/c26462.md) -C26462 için açıklama ve örnek eklendi
- [`C26461 USE_CONST_POINTER_ARGUMENTS:`](../code-quality/c26461.md) -C26461 için açıklama ve örnek eklendi
- [`C26460 USE_CONST_REFERENCE_ARGUMENTS`](../code-quality/c26460.md) -C26460 için açıklama ve örnek eklendi
- [`C26440 DECLARE_NOEXCEPT`](../code-quality/c26440.md) -C26440 için temel yönergelere örnek ve bağlantı eklendi
- [`C26439 SPECIAL_NOEXCEPT`](../code-quality/c26439.md) -C26439 için temel yönergelere örnek ve bağlantı eklendi
- [`C26436 NEED_VIRTUAL_DTOR`](../code-quality/c26436.md) -C26436 ' e eklenen örnek ve çekirdek yönergeleri
- [`C26408 NO_MALLOC_FREE`](../code-quality/c26408.md) -C26408 ' e eklenen örnek ve çekirdek yönergeleri
- [`C26401 DONT_DELETE_NON_OWNER`](../code-quality/c26401.md) -C26401 ' e eklenen örnek ve çekirdek yönergeleri
- [`C26494 VAR_USE_BEFORE_INIT`](../code-quality/c26494.md) -C26494 'e örnek eklendi
- [`C26493 NO_CSTYLE_CAST`](../code-quality/c26493.md) -C26493 'e örnek eklendi
- [`C26492 NO_CONST_CAST`](../code-quality/c26492.md) -C26492 'e örnek eklendi
- [`C26490 NO_REINTERPRET_CAST`](../code-quality/c26490.md) -C26490 'e örnek eklendi
- [`C26482 NO_DYNAMIC_ARRAY_INDEXING`](../code-quality/c26482.md) -C26482 'e örnek eklendi
- [`C26471 NO_REINTERPRET_CAST_FROM_VOID_PTR`](../code-quality/c26471.md) -C26471 'e örnek eklendi
- [`C26466 NO_STATIC_DOWNCAST_POLYMORPHIC`](../code-quality/c26466.md) -C26466 'e örnek eklendi
- [`C26465 NO_CONST_CAST_UNNECESSARY`](../code-quality/c26465.md) -C26465 'e örnek eklendi
- [`C26447 DONT_THROW_IN_NOEXCEPT`](../code-quality/c26447.md) -C26447 'e örnek ekleme
- [`C26446 USE_GSL_AT`](../code-quality/c26446.md) -C26446 için bir örnek eklendi
- [`C26434 DONT_HIDE_METHODS`](../code-quality/c26434.md) -C26434 için örnek eklendi
- [`C26432 DEFINE_OR_DELETE_SPECIAL_OPS`](../code-quality/c26432.md) -C26432 için örnek eklendi
- [`C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT`](../code-quality/c26402.md) -C26402 için örnek eklendi
- [`C26409 NO_NEW_DELETE`](../code-quality/c26409.md) -C26409 için örnek eklendi
- [`C26474 NO_IMPLICIT_CAST`](../code-quality/c26474.md) -Temel/türetilmiş durumları netleştirmek için C26474 güncelleştirildi
## <a name="linux-with-microsoft-c-in-visual-studio"></a>Visual Studio 'da Microsoft C++ ile Linux

### <a name="new-articles"></a>Yeni makaleler

- [Visual Studio 'da Linux CMake projesi yapılandırma](../linux/cmake-linux-configure.md)

### <a name="updated-articles"></a>Güncelleştirilmiş makaleler

- [Visual Studio 'Da Linux MSBuild C++ projesi oluşturma](../linux/create-a-new-linux-project.md) -güncelleştiren yönergeler bir Linux projesi oluşturma
- [ConnectionManager başvurusu](../linux/connectionmanager-reference.md) -değiştirme, temizleme için komutlar eklendi
- [Visual Studio 'Da Linux CMake projesi yapılandırma](../linux/cmake-linux-configure.md) -en son kullanıcı arabirimini yansıtacak şekilde güncelleştirildi
- [Linux MSBuild projenizi dağıtma, çalıştırma ve hata ayıklama](../linux/deploy-run-and-debug-your-linux-project.md) -eklendi `GDB Path`

## <a name="cc-compiler-and-tools-errors-and-warnings"></a>C/C++ derleyicisi ve araçları hataları ve uyarıları

### <a name="new-articles"></a>Yeni makaleler

- [Derleyici Uyarısı (düzey 4) C4388](../error-messages/compiler-warnings/c4388.md) -eklenen uyarı C4388, güncelleştirilmiş 16,7 uyarıları

### <a name="updated-articles"></a>Güncelleştirilmiş makaleler

- [Derleyici Uyarısı (düzey 3) C4018](../error-messages/compiler-warnings/compiler-warning-level-3-c4018.md) -güncelleştirilmiş 16,7 uyarıları
- [Derleyici Uyarısı (düzey 4) C4389](../error-messages/compiler-warnings/compiler-warning-level-4-c4389.md) -güncelleştirilmiş 16,7 uyarıları
- [Derleyici sürümüne göre derleyici uyarıları](../error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md) -güncelleştirilmiş 16,7 uyarıları
- [Derleyici uyarıları C4800 Ile C5999](../error-messages/compiler-warnings/compiler-warnings-c4800-through-c4999.md) -güncelleştirilmiş 16,7 uyarıları
- [Derleyici hatası C3381](../error-messages/compiler-errors-2/compiler-error-c3381.md) -adres cpp-docs 2493; güncelleştirme açıklamaları ve örnek

## <a name="cc-compiler-intrinsics-and-assembly-language"></a>C/C++ Derleyici iç bilgileri ve derleme dili

### <a name="updated-articles"></a>Güncelleştirilmiş makaleler

- [Visual Studio 'da C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md) -16,8 sürüm notlarına güncelleştirildi
- [Microsoft C/C++ yardım ve topluluk](../overview/visual-cpp-help-and-community.md) tarafından güncelleştirilmiş devcom ve bağlantı&Microsoft docs Q
- [Visual Studio 'da C++](../overview/visual-cpp-in-visual-studio.md) -güncelleştirilmiş devcom ve Microsoft Docs Q&bağlantı
- [Microsoft c++ dil uygunluğu tablosu](../overview/visual-cpp-language-conformance.md) -güncelleştirilmiş C++ 20 kitaplığı uyumluluk tablosu, güncelleştirme dil özelliği tablosu 16,7

## <a name="c-in-visual-studio"></a>Visual Studio’da C++

### <a name="updated-articles"></a>Güncelleştirilmiş makaleler

- [`__restrict`](../cpp/extension-restrict.md)
- [if-else deyimidir (C++)](../cpp/if-else-statement-cpp.md) -dilbilgisi için açıklama eklendi `if/else`
- [`union`](../cpp/unions.md) -Sabit kod parçacığı

## <a name="cc-projects-and-build-systems"></a>C/C++ projeleri ve derleme sistemleri

### <a name="new-articles"></a>Yeni makaleler

- [`.vcxproj` dosyalar ve joker karakterler](../build/reference/vcxproj-files-and-wildcards.md)
- [`/headerUnit` (IBC başlık birimini kullan)](../build/reference/headerunit.md)
- [`/module:exportHeader` (Üst bilgi birimleri oluştur)](../build/reference/module-exportheader.md)
- [`/module:reference` (Adlandırılmış modül ıFC kullanın)](../build/reference/module-reference.md)
- [`/translateInclude` (İçeri aktarma yönergeleri içine çeviri ekleme yönergeleri)](../build/reference/translateinclude.md)
- [`/Zc:preprocessor` (Önişlemci uyumluluk modunu etkinleştir)](../build/reference/zc-preprocessor.md)

### <a name="updated-articles"></a>Güncelleştirilmiş makaleler

- [ `/permissive-` (Standartlar uyumluluğu)](../build/reference/permissive-standards-conformance.md) -16,8 sürüm notlarına güncelleştirildi
- [ `/clr` (Ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) -için açıklama eklendi`/clr`
- [pgosüpürme](../build/pgosweep.md) -daha fazla pgotarama seçeneği eklendi
- [Kullanarak `__declspec(dllimport)` verileri içeri aktarma](../build/importing-data-using-declspec-dllimport.md) -Güncelleştirilmiş örnek

## <a name="c-porting-and-upgrade-guide"></a>C++ taşıma ve Yükseltme Kılavuzu

### <a name="updated-articles"></a>Güncelleştirilmiş makaleler

- [Nasıl yapılır: mevcut C++ kodunu bir Evrensel Windows platformu uygulamasında kullanma](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md) -netlik ve güncelleştirilmiş örnekler için yeniden çalıştı

## <a name="c-standard-library-stl-reference"></a>C++ standart kitaplığı (STL) başvurusu

### <a name="new-articles"></a>Yeni makaleler

- [`<bit>`](../standard-library/bit.md)
- [`<bit>` lerdir](../standard-library/bit-functions.md)
- [`endian` yardımının](../standard-library/bit-enum.md)

### <a name="updated-articles"></a>Güncelleştirilmiş makaleler

- [ `<ios>` tür tanımları](../standard-library/ios-typedefs.md) -GitHub başına güncelleştirilmiş örnek #2514
- [ `basic_string` Sınıf](../standard-library/basic-string-class.md) eklendi `startswith()` ,`endswith()`
- [`ios_base Class`](../standard-library/ios-base-class.md)
- [`map` sınıfı](../standard-library/map-class.md)
- [ `multimap` Sınıf](../standard-library/multimap-class.md) eklendi`contains()`
- [ `multiset` Sınıf](../standard-library/multiset-class.md) eklendi`contains()`
- [ `set` Sınıf](../standard-library/set-class.md) eklendi`contains()`
- [ `unordered_map` Sınıf](../standard-library/unordered-map-class.md) eklendi`contains()`
- [ `unordered_multimap` Sınıf](../standard-library/unordered-multimap-class.md) eklendi`contains()`
- [ `unordered_multiset` Sınıf](../standard-library/unordered-multiset-class.md) eklendi`contains()`
- [ `unordered_set` Sınıf](../standard-library/unordered-set-class.md) eklendi`contains()`
- [ `basic_string_view` Sınıf](../standard-library/basic-string-view-class.md) eklendi `startswith()` ,`endswith()`
- [ `<bit>` işlevler](../standard-library/bit-functions.md) -güncelleştirilmiş `nodiscard` sözdizimi

## <a name="community-contributors"></a>Topluluk katkı sağlayanlar

Aşağıdaki kişiler bu süre boyunca C++, C ve assembler belgelerine katkıda bulunanlar. Teşekkür ederiz! Nasıl katkıda bulunabileceğinizi öğrenmek isterseniz bkz. katkıda [bulunan kılavuzuna genel bakış Microsoft docs](https://docs.microsoft.com/contribute/) .

- [yecril71pl](https://github.com/yecril71pl) -Christopher Yeliighton (4)
- [definedris-](https://github.com/definedrisk) ben (3)
- [Yatak balığı](https://github.com/BeardedFish) -Darian B. (1)
- [codevenkat](https://github.com/codevenkat) (1)
- [eltociear](https://github.com/eltociear) -Ikko Ashimine (1)
- [fsb4000](https://github.com/fsb4000) -Igor Zhukov (1)
- [Jaiganeshkumaran](https://github.com/Jaiganeshkumaran) -Jaiganesh Kumaran (1)
- [jogo-](https://github.com/jogo-) (1)
- yer [tanotheranonymoususer](https://github.com/justanotheranonymoususer) (1)
- [matrohin](https://github.com/matrohin) -Dmitry Matrokhın (1)
- [mhemmit](https://github.com/mhemmit) (1)
- [MSDN-beyaz gece](https://github.com/MSDN-WhiteKnight) -MSDN. Beyaz gece (1)
- [Odintemple](https://github.com/OdinTemple) -ODIN Temple (1)
- [r00tdr4g0n](https://github.com/r00tdr4g0n) -r00tdr4g0n (1)
- [sebkseemer](https://github.com/sebkraemer) -Sebastian Krämer (1)
- [vtjnash](https://github.com/vtjnash) -Jameson Nash (1)
- [Youssef1313](https://github.com/Youssef1313) -Youssef Victor (1)
- [zecozephyr](https://github.com/zecozephyr) -Jonathan Bailey (1)