---
description: 'Daha fazla bilgi edinin: CString bağımsız değişken geçirme'
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
ms.openlocfilehash: ee47898ffdfc5129b11b0f9480669fa142d12818
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167181"
---
# <a name="cstring-argument-passing"></a>CString bağımsız değişken geçirme

Bu makalede [CString](../atl-mfc-shared/reference/cstringt-class.md) nesnelerinin işlevlere nasıl geçirilebileceği ve işlevlerden nesnelerin nasıl döndürüleneceği açıklanmaktadır `CString` .

## <a name="cstring-argument-passing-conventions"></a><a name="_core_cstring_argument.2d.passing_conventions"></a> CString Argument-Passing kuralları

Bir sınıf arabirimi tanımladığınızda, üye işlevleriniz için bağımsız değişken geçirme kuralını belirlemelisiniz. Nesneleri geçirmek ve döndürmek için bazı standart kurallar vardır `CString` . [Dizelerde Işlev girişleri](#_core_strings_as_function_inputs) ve [dizeler olarak işlev çıkışları](#_core_strings_as_function_outputs)olarak açıklanan kuralları izlerseniz, etkili, doğru kodunuz olur.

## <a name="strings-as-function-inputs"></a><a name="_core_strings_as_function_inputs"></a> Işlev girişleri olarak dizeler

Çağrılan işlevlerde bir nesne kullanmanın en etkili ve güvenli yolu, `CString` işleve bir nesne geçirmektir `CString` . Ada rağmen, bir `CString` nesne bir dizeyi, null Sonlandırıcı Içeren C stili dize olarak dahili olarak depolamaz. Bunun yerine, bir `CString` nesnesi, sahip olduğu karakter sayısını dikkatle izler. `CString`Null ile sonlandırılmış bir dize için BIR LPCTSTR işaretçisi sağlamak, kodunuzun sürekli olarak yapması durumunda önemli hale gelebilmesi için az miktarda iş olabilir. İçerikte yapılan herhangi bir değişiklik, `CString` LPCTSTR işaretçisinin eski kopyalarını geçersiz hale yaptığından sonuç geçicidir.

Bir C stili dize sağlamak için bazı durumlarda bunun mantıklı olduğunu unutmayın. Örneğin, çağrılan bir işlevin C dilinde yazıldığı ve nesneleri desteklemediği bir durum olabilir. Bu durumda, `CString` parametresini LPCTSTR öğesine ve işlev, C stili null ile sonlandırılmış bir dize alır. Ayrıca, bir `CString` `CString` C stili dize parametresini kabul eden oluşturucuyu kullanarak diğer yöne gidebilir ve bir nesne oluşturabilirsiniz.

Dize içeriği bir işlev tarafından değiştirilebiliyorsa, parametreyi sabit olmayan bir `CString` başvuru () olarak bildirin `CString&` .

## <a name="strings-as-function-outputs"></a><a name="_core_strings_as_function_outputs"></a> Işlev çıkışları olarak dizeler

Genellikle nesneler, `CString` `CString` temel türler gibi değer semantiğini izlediğinden, işlevlerden nesneleri döndürebilirsiniz. Salt okunurdur bir dize döndürmek için sabit bir `CString` başvuru ( `const CString&` ) kullanın. Aşağıdaki örnek, `CString` parametrelerin ve dönüş türlerinin kullanımını göstermektedir:

[!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
