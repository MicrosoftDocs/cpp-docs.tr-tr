---
description: 'Hakkında daha fazla bilgi edinin: hangi dışarı aktarma yönteminin kullanılacağını belirleme'
title: Hangi dışarı aktarma yönteminin kullanılacağını belirleme
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- exporting DLLs [C++], method comparison
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
ms.openlocfilehash: 5d9e973d331ebd6190cd8e2a46601dfe2b057d09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162982"
---
# <a name="determine-which-exporting-method-to-use"></a>Hangi dışarı aktarma yönteminin kullanılacağını belirleme

İşlevleri bir. def dosyası ya da anahtar sözcüğü olmak üzere iki şekilde dışarı aktarabilirsiniz `__declspec(dllexport)` . DLL 'niz için ne kadar iyi bir yönteme karar vermenize yardımcı olması için aşağıdaki soruları göz önünde bulundurun:

- Daha sonra daha fazla işlev dışarı aktarmayı planlıyor musunuz?

- DLL 'niz yalnızca yeniden derleyebilirsiniz veya yeniden derlenemez uygulamalar tarafından kullanılıyor — Örneğin, üçüncü taraflar tarafından oluşturulan uygulamalar.

## <a name="pros-and-cons-of-using-def-files"></a>. Def dosyalarını kullanmanın uzmanları ve dezavantajları

Bir. def dosyasındaki işlevleri dışarı aktarmak, dışa aktarma sıra sayıları üzerinde denetim sağlar. DLL 'nize bir içe aktarılmış işlev eklediğinizde, bu değeri diğer tüm içe aktarılmış fonksiyondan daha yüksek bir sıra değeri atayabilirsiniz. Bunu yaptığınızda, örtük bağlama kullanan uygulamaların, yeni işlevi içeren içeri aktarma kitaplığıyla yeniden bağlanması gerekmez. Yeni işlevler ekleyebildiğiniz ve aynı zamanda kendisine ait olan uygulamalarla düzgün şekilde çalışmaya devam ettiğinden emin olduğunuzdan, çok sayıda uygulama tarafından kullanılmak üzere bir DLL tasarlıyorsanız bu çok kullanışlı olur. Örneğin, MFC DLL 'Leri. def dosyaları kullanılarak oluşturulur.

Bir. def dosyası kullanmanın başka bir avantajı da, `NONAME` bir işlevi dışarı aktarmak için özniteliğini kullanmanıza olanak sağlar. Bu, yalnızca DLL 'deki dışarı aktarmalar tablosuna sıra koyar. Çok sayıda aktarılmış işlevi olan DLL 'Ler için, `NONAME` özniteliğini kullanarak dll dosyasının boyutu azalabilir. Modül tanımı deyimi yazma hakkında daha fazla bilgi için bkz. [Module-Definition deyimleri kuralları](reference/rules-for-module-definition-statements.md). Sıralı dışarı aktarma hakkında daha fazla bilgi için bkz. [DLL 'Den Işlevleri ad yerine sıraya göre dışarı aktarma](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

Bir. def dosyası kullanmanın dezavantajı, bir C++ dosyasındaki işlevleri dışarı aktarıyorsanız, düzenlenmiş adları. def dosyasına yerleştirmeniz veya MSVC derleyicisi tarafından gerçekleştirilen ad dekorasyonu kaçınmak için extern "C" kullanarak dışarı aktarılan işlevleri tanımlamanız gerekir.

Düzenlenmiş adları. def dosyasına yerleştirirseniz, bunları [dumpbin](reference/dumpbin-reference.md) aracını kullanarak veya bağlayıcı [/map](reference/map-generate-mapfile.md) seçeneğini kullanarak elde edebilirsiniz. Derleyici tarafından üretilen düzenlenmiş adlar derleyiciye özeldir; Bu nedenle, derleyici tarafından üretilen düzenlenmiş adları. def dosyasına yerleştirirseniz, çağıran uygulamadaki düzenlenmiş adların DLL 'nin. def dosyasındaki adı eşleşen adlarla eşleşmesi için DLL 'ye bağlanan uygulamalar aynı derleyici sürümü kullanılarak da oluşturulmalıdır.

## <a name="pros-and-cons-of-using-__declspecdllexport"></a>__Declspec (dllexport) kullanmanın uzmanları ve dezavantajları

`__declspec(dllexport)`,. Def dosyasını sürdürme ve dışarıya aktarılmış işlevlerin düzenlenmiş adlarını alma hakkında endişelenmeniz olmadığından, kullanımı uygundur. Ancak, bu şekilde dışa aktarma işleminin yararlılığı, yeniden oluşturmak istediğiniz bağlantılı uygulama sayısıyla sınırlıdır. DLL 'yi yeni dışarı aktarımlarla yeniden oluşturursanız, dışarı aktarılan C++ işlevlerine yönelik düzenlenmiş adlar, derlemeyi yeniden oluşturmak için farklı bir derleyici sürümü kullanıyorsanız, uygulamaları yeniden oluşturmanız da gerekir.

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Kullanarak DLL 'den dışarı aktarın. DEF dosyaları](exporting-from-a-dll-using-def-files.md)

- [__Declspec (dllexport) kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak dışarı ve içeri aktarma](exporting-and-importing-using-afx-ext-class.md)

- [C Dili Çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C veya C++ Dili Çalıştırılabilirlerinde kullanmak için C işlevlerini dışarı aktarma](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 'yi başlatma](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Satır içi işlevleri içeri ve dışarı aktarma](importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](mutual-imports.md)

- [Düzenlenmiş adlar](reference/decorated-names.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](exporting-from-a-dll.md)
