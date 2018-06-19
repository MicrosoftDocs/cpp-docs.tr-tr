---
title: CString bağımsız değişken geçirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 642ff20028a0929bb7bc11815e66b9f845ef9bd7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356836"
---
# <a name="cstring-argument-passing"></a>CString bağımsız değişken geçirme
Bu makalede nasıl geçirileceğini açıklayan [CString](../atl-mfc-shared/reference/cstringt-class.md) nesneleri işlevleri ve nasıl döndürüleceğini `CString` işlevleri nesneleri.  
  
##  <a name="_core_cstring_argument.2d.passing_conventions"></a> CString bağımsız değişken geçirme kuralları  
 Bir sınıf arabirimi tanımladığınızda, üye işlevleri için bağımsız değişken geçirme kuralı belirlemeniz gerekir. Geçirme ve döndürmek için standart bazı kurallar vardır `CString` nesneleri. Açıklanan kuralları izlerseniz [dizeleri işlev giriş olarak](#_core_strings_as_function_inputs) ve [dizeleri işlevi çıktı olarak](#_core_strings_as_function_outputs), verimli ve doğru koduna sahip olacak.  
  
##  <a name="_core_strings_as_function_inputs"></a> İşlev giriş olarak dizeleri  
 Kullanmak için en güvenli ve verimli şekilde bir `CString` çağrılan işlevlerin nesnedir geçirmek için bir `CString` işlevine nesnesi. Ad rağmen bir `CString` nesne saklamadığı bir dize dahili olarak null Sonlandırıcı sahip C stili dize olarak. Bunun yerine, bir `CString` nesne olan karakter sayısı dikkatli izini tutar. Sahip `CString` sağlayan bir `LPCTSTR` null sonlandırılmış bir dize işaretçidir sürekli yapmak, kodunuzu varsa, önemli hale gelebilir iş az miktarda. Değişiklik sonucu geçici çünkü `CString` içeriği geçersiz kılar, eski kopyalarını `LPCTSTR` işaretçi.  
  
 Bir C stili dize sağlamak için bazı durumlarda algılama yapar. Örneğin, burada çağrılan işlev C'de yazılmış ve nesneleri desteklemiyor bir durum olabilir. Bu durumda, coerce `CString` parametresi `LPCTSTR`, ve işlev C türü null sonlandırılmış bir dize alır. Ayrıca başka bir yöne gidin ve oluşturma bir `CString` kullanarak nesne `CString` C stili dize parametresi kabul Oluşturucusu.  
  
 Dize içeriklerini bir işlev tarafından değiştirilmesi gerekiyorsa, bir nonconstant parametre bildirme `CString` başvurusu (**CString &**).  
  
##  <a name="_core_strings_as_function_outputs"></a> Dize olarak işlevi çıkışları  
 Genellikle döndürebilir `CString` çünkü işlevlerden nesneleri `CString` nesneleri değer semantiği ilkel türler gibi izleyin. Salt okunur bir dize döndürecek şekilde bir sabit kullanın `CString` başvurusu (**const CString &**). Aşağıdaki örnek kullanımını göstermektedir `CString` parametreler ve dönüş türleri:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

