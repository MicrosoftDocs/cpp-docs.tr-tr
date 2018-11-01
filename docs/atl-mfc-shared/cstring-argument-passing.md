---
title: CString bağımsız değişken geçirme
ms.date: 11/04/2016
helpviewer_keywords:
- strings [C++], as function input/output
- argument passing [C++]
- arguments [C++], passing
- functions [C++], strings as input/output
- argument passing [C++], C strings
- passing arguments, C strings
- CString objects, passing arguments
- string arguments
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
ms.openlocfilehash: bf18265e19e4b1c1db010a4d7638fa959c357bca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562402"
---
# <a name="cstring-argument-passing"></a>CString bağımsız değişken geçirme

Bu makalede nasıl geçirileceğini açıklar [CString](../atl-mfc-shared/reference/cstringt-class.md) nesneleri işlevleri ve nasıl döndürüleceğini `CString` işlevleri nesneleri.

##  <a name="_core_cstring_argument.2d.passing_conventions"></a> CString bağımsız değişken geçirme kuralları

Bir sınıf arabirimi tanımladığınızda, üye işlevleri için bağımsız değişken geçirme kuralı belirlemeniz gerekir. İletme ve döndürme için bazı standart kuralları `CString` nesneleri. İçinde açıklanan kurallar izlerseniz [dize işlev giriş olarak](#_core_strings_as_function_inputs) ve [işlevi çıktı olarak dizeler](#_core_strings_as_function_outputs), verimli ve doğru bir kod olacaktır.

##  <a name="_core_strings_as_function_inputs"></a> Dize olarak işlev giriş

Kullanılacak en verimli ve güvenli bir yol bir `CString` çağrılan işlevlerin nesnedir geçirilecek bir `CString` işlevi nesnesi. Adını rağmen bir `CString` nesne depolamaz bir dize dahili olarak bir null Sonlandırıcı sahip C stili dize olarak. Bunun yerine, bir `CString` nesne dikkatli izini bulunan karakter sayısını tutar. Sahip `CString` LPCTSTR null ile sonlandırılmış bir dize işaretçisi sürekli yapmak kodunuz varsa, belirgin hale gelebilir iş az miktarda sağlar. Değişiklik için sonucu geçici `CString` içeriği LPCTSTR işaretçi eski kopyalarını geçersiz kılar.

Bu bazı durumlarda bir C tarzı dize sağlamak mantıklı. Örneğin, bir durum burada çağrılan işlev C dilinde yazılan ve nesneleri desteklemiyor olabilir. Bu durumda, coerce `CString` LPCTSTR ve işlev parametresi, C stili null ile sonlandırılmış bir dize alırsınız. Ayrıca diğer yönde gidin ve oluşturma bir `CString` kullanarak nesne `CString` C stili dize parametresi kabul eden Oluşturucu.

Dize içeriklerini işlev tarafından değiştirilmesi gerekiyorsa, parametre olarak bir nonconstant bildirmek `CString` başvurusu (`CString&`).

##  <a name="_core_strings_as_function_outputs"></a> İşlev çıktı olarak dizeler

Genellikle döndürebilir `CString` çünkü nesneler işlevlerden `CString` nesneler gibi ilkel türler değer semantiği izleyin. Salt okunur bir dize döndürecek şekilde, bir sabiti kullanın `CString` başvurusu (`const CString&`). Aşağıdaki örnek, kullanımını gösterir `CString` parametreler ve dönüş türleri:

[!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

