---
title: CString Bağımsız Değişken Geçirme
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
ms.openlocfilehash: 53977eb47520a20571a2d5ba8aa105c567ff40d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317926"
---
# <a name="cstring-argument-passing"></a>CString Bağımsız Değişken Geçirme

Bu makalede, [CString](../atl-mfc-shared/reference/cstringt-class.md) nesnelerinin işlevlere nasıl `CString` geçirilen ve nesnelerin işlevlerden nasıl döndürülecekolduğu açıklanmaktadır.

## <a name="cstring-argument-passing-conventions"></a><a name="_core_cstring_argument.2d.passing_conventions"></a>CString Bağımsız Değişken-Geçen Sözleşmeler

Bir sınıf arabirimi tanımladığınızda, üye işlevleriniz için bağımsız değişken geçen kuralı belirlemeniz gerekir. Nesneleri geçirmek ve döndürmek `CString` için bazı standart kurallar vardır. [Dizeleri İşlev Girişleri](#_core_strings_as_function_inputs) ve [Strings işlev çıkışları olarak](#_core_strings_as_function_outputs)açıklanan kuralları izlerseniz, verimli, doğru kod olacaktır.

## <a name="strings-as-function-inputs"></a><a name="_core_strings_as_function_inputs"></a>İşlev Girişi Olarak Dizeleri

Çağrılan işlevlerde bir `CString` nesneyi kullanmanın en verimli `CString` ve güvenli yolu, bir nesneyi işleve geçirmektir. Ada rağmen, `CString` bir nesne bir dize yi null terminator'u olan C stili dize olarak dahili olarak depolamaz. Bunun yerine, bir `CString` nesne sahip olduğu karakter sayısını dikkatli bir şekilde izler. Geçersiz `CString` sonlandırılan bir dize için lpctstr işaretçisi sağlamak, kodunuzu sürekli yapmak zorunda ysa önemli hale gelebilir iş küçük bir miktardır. `CString` İçeriğindeki herhangi bir değişiklik LPCTSTR işaretçisinin eski kopyalarını geçersiz kıldığı için sonuç geçicidir.

Bazı durumlarda C stili dize sağlamak mantıklı. Örneğin, çağrılan işlevin C'de yazıldığı ve nesneleri desteklemediği bir durum olabilir. Bu durumda, parametreyi `CString` LPCTSTR'e zorlarsınız ve işlev C stili null-terminatedli dize alır. C stili dize parametresini `CString` kabul eden `CString` oluşturucuyu kullanarak diğer yöne gidebilir ve nesne oluşturabilirsiniz.

Dize içeriği bir işlev tarafından değiştirilecekse, parametreyi `CString` sabit`CString&`olmayan bir başvuru olarak bildirin ( ).

## <a name="strings-as-function-outputs"></a><a name="_core_strings_as_function_outputs"></a>İşlev Çıktısı Olarak Dizeleri

Nesneler ilkel türleri `CString` gibi değer `CString` semantikleri izleyin, çünkü genellikle işlevleri nesneleri döndürebilirsiniz. Salt okunur dizesini döndürmek için `CString` sabit`const CString&`bir başvuru ( ). Aşağıdaki örnekte parametrelerin `CString` ve iade türlerinin kullanımı gösteriş verilmiştir:

[!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Dizeleri (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
