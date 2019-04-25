---
title: Hangi dışarı aktarma metodunun kullanılacağını belirleme
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- exporting DLLs [C++], method comparison
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
ms.openlocfilehash: 974c32cef87801599ba0d14fd146e84ad874467f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273743"
---
# <a name="determine-which-exporting-method-to-use"></a>Hangi dışarı aktarma metodunun kullanılacağını belirleme

İki yöntemden biriyle işlevleri dışa aktarabilirsiniz — bir .def dosyası veya `__declspec(dllexport)` anahtar sözcüğü. Hangi DLL dosyanız için daha iyi bir yoludur karar vermenize yardımcı olmak için aşağıdaki soruları göz önünde bulundurun:

- Daha sonra daha fazla işlevleri dışarı aktarmak planlıyor musunuz?

- Yeniden oluşturabilirsiniz veya yeniden oluşturulamıyor uygulamalar tarafından kullanıldığı uygulamalar tarafından kullanılan, DLL — Örneğin, üçüncü taraflarca oluşturulan uygulamaları?

## <a name="pros-and-cons-of-using-def-files"></a>Artıları ve eksileri .def dosyaları kullanma

Dışa aktarma işlevlerini dışa aktarma sıra sayıları üzerinde denetim bir .def dosyası sağlar. DLL dosyanız için dışa aktarılan bir işlevin eklediğinizde, verilen herhangi bir işlevi daha yüksek sıralı bir değerden atayabilirsiniz. Bunu yaptığınızda, örtük bağlama kullanan uygulamaları içeren yeni bir işlev içeri aktarma kitaplığı ile yeniden Bağla gerekmez. Birçok uygulama tarafından kullanılacak bir DLL tasarlıyorsanız, yeni işlevler eklemek ve ayrıca, zaten kullanmakta uygulamaları ile düzgün çalışmak devam etmesini sağlamak için çok kullanışlı bir yoldur. Örneğin, MFC DLL .def dosyalarını kullanarak oluşturulur.

Bir .def dosyası kullanarak başka bir avantajı, kullanabileceğiniz olduğu `NONAME` bir işlevi dışa aktarmak için özniteliği. Bu, yalnızca DLL dışarı aktarma tablosundaki koyar. Dışarı aktarılan işlevleri, çok sayıda sahip kullanarak DLL'ler için `NONAME` özniteliği, DLL dosyasının boyutunu azaltabilirsiniz. Bir modül tanımlama deyimini yazma hakkında daha fazla bilgi için bkz: [modül tanımlama deyimleri kuralları](reference/rules-for-module-definition-statements.md). Sıralı dışarı aktarma hakkında daha fazla bilgi için bkz: [DLL'den işlevleri yerine ada göre bir DLL](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

Bir .def dosyası kullanılarak dezavantajı C++ dosyasındaki işlevleri dışa aktarıyorsanız, düzenlenmiş adları .def koymak ya da sahip dosya yapmış ad düzenleme istemiyorsanız extern "C" kullanarak dışarı aktarılan işlevleri tanımlayın, mi MSVC derleyici tarafından.

Düzenlenmiş adları .def dosyasına yerleştirirseniz, bunları kullanarak alabilirsiniz [DUMPBIN](reference/dumpbin-reference.md) aracını veya bağlayıcı [/MAP](reference/map-generate-mapfile.md) seçeneği. Derleyici tarafından üretilen düzenlenmiş adların derleyiciye özel; düzenlenmiş adları .def dosyasına derleyici tarafından üretilen koyarsanız, bu nedenle, DLL için bağlantı veren uygulamalar da böylece uygulamadaki düzenlenmiş adlar dışarı aktarılan eşleşen derleyici aynı sürümünü kullanarak oluşturulması gereken i adları n DLL'nin .def dosyası.

## <a name="pros-and-cons-of-using-declspecdllexport"></a>Artıları ve eksileri __declspec(dllexport) kullanarak

Kullanarak `__declspec(dllexport)` koruma .def dosyası ve düzenlenmiş adlar dışarı aktarılan işlevlerin edinme hakkında endişelenmeye gerek olmadığı için uygundur. Ancak, bu şekilde, verme kullanışlılığını yeniden derlemek hazır olduğunuz bağlı uygulamaların sayısı sınırlıdır. DLL yeni dışarı aktarma ile yeniden oluşturursanız, ayrıca uygulamaları için C++ işlevlerini dışa aktarılan düzenlenmiş adlar yeniden oluşturmak için farklı bir derleyici sürümü kullanırsanız değişebileceğinden yeniden gerekir.

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Kullanarak bir DLL dışarı aktarın. DEF dosyaları](exporting-from-a-dll-using-def-files.md)

- [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarma](exporting-and-importing-using-afx-ext-class.md)

- [C dili çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C veya C++ dili çalıştırılabilirlerinde kullanmak için C işlevlerini dışa aktarma](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [DLL'yi Başlat](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Satır içi işlevleri içeri ve dışarı aktarma](importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](mutual-imports.md)

- [Düzenlenmiş adlar](reference/decorated-names.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](exporting-from-a-dll.md)
