---
title: DEF dosyaları kullanarak DLL'den dışarı aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
- exporting DLLs [C++], DEF files
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a870df7ea803813a8403cd807c0f0612873d4576
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369753"
---
# <a name="exporting-from-a-dll-using-def-files"></a>DEF Dosyaları Kullanarak DLL'den Dışarı Aktarma
Bir modül-tanımlama (.def) dosyası, DLL çeşitli özniteliklerini tanımlayan bir veya daha fazla modül deyimi içeren bir metin dosyasıdır. Kullanmıyorsanız, **__declspec(dllexport)** DLL işlevlerini dışarı aktarmak için anahtar sözcüğü DLL .def dosyası gerektirir.  
  
 En az .def dosyası aşağıdaki modül tanımlama deyimleri içermelidir:  
  
-   İlk ifade dosyasındaki kitaplığı deyim olmalıdır. Bu deyim bir DLL'e ait olarak .def dosyası tanımlar. KİTAPLIK deyimi DLL adı tarafından izlenir. Bağlayıcı, bu adı DLL'in içeri aktarma kitaplığı'nda yerleştirir.  
  
-   EXPORTS deyimi adlarını ve isteğe bağlı olarak, DLL tarafından dışarı aktarılan işlevlerin sıralı değerlerini listeler. İşlevin adı ile izleyerek bir sıra sayısı değerini atadığınız işlevi bir at işareti (@) ve bir sayı. Sıralı değerler belirttiğinizde, burada N DLL tarafından dışarı aktarılan işlevlerin sayısını alır ile 1 aralığında olması gerekir. İşlevler sıralı olarak dışarı aktarmak istiyorsanız, bkz: [dışarı aktarma işlevleri DLL'den göre sıralı yerine ada göre](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) yanı sıra bu konuda.  
  
 Örneğin, ikili arama ağacını uygulamak için kod içeren DLL aşağıdakine benzeyebilir:  
  
```  
LIBRARY   BTREE  
EXPORTS  
   Insert   @1  
   Delete   @2  
   Member   @3  
   Min   @4  
```  
  
 Kullanırsanız [MFC DLL Sihirbazı](../mfc/reference/mfc-dll-wizard.md) bir MFC DLL oluşturmak için sihirbaz iskelet .def dosyası sizin için oluşturur ve otomatik olarak projenize ekler. Bu dosyaya dışarı aktarılacak olan işlevlerin adlarını ekleyin. MFC dışı DLL'ler için kendiniz .def dosyası oluşturun ve bunu projenize ekleyin.  
  
 İşlevlerinizi C++ dosyasına dışa aktarıyorsanız, ya düzenlenmiş adları .def dosyasına yerleştirin veya extern "C" kullanarak standart C bağlantısı ile dışarı aktarılan işlevlerinizi tanımlamanız gerekir. Düzenlenmiş adlar .def dosyasına yerleştirmek ihtiyacınız varsa, bunları kullanarak elde edebilirsiniz [DUMPBIN](../build/reference/dumpbin-reference.md) bağlayıcı kullanarak veya aracı [/MAP](../build/reference/map-generate-mapfile.md) seçeneği. Derleyici tarafından üretilen düzenlenmiş adlar derleyici belirli olduğuna dikkat edin. Visual C++ derleyicisi tarafından oluşturulan bir .def dosyası düzenlenmiş adlar yerleştirirseniz, DLL bağlantı veren uygulamalar ayrıca çağıran uygulamadaki düzenlenmiş adlar dışa aktarılan DLL .de adlarıyla böylece Visual C++ aynı sürümü kullanılarak oluşturulmalıdır f dosyası.  
  
 Oluşturmakta olduğunuz varsa bir [uzantı DLL](../build/extension-dlls-overview.md), ve bir .def dosyası kullanarak dışa aktarma yerleştirin aşağıdaki kod, dışarı aktarılan sınıfları içeren başlık dosyalarının başında ve sonunda:  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
 Bu satırlar, dahili olarak kullanılan veya, sınıflarınızı eklenen MFC değişken olduğundan emin olun (veya dışarı içe), MFC uzantı DLL. Örneğin, bir sınıf kullanarak türetilirken `DECLARE_DYNAMIC`, eklemek için makro genişler bir `CRuntimeClass` sınıfınıza üye değişkeni. Bu dört satırı dışarıda bırakarak, DLL derleme veya yanlış bağlantı ya da istemci uygulaması DLL'e bağlantıları değiştiğinde hataya neden neden olabilir.  
  
 DLL oluştururken, bağlayıcı dışarı aktarma (.exp) dosyası oluşturmak için .def dosyası ve bir içeri aktarma kitaplığı (.lib) dosyası kullanır. Bağlayıcı sonra DLL dosyasını oluşturmak için dışa aktarma dosyası kullanır. Oluşturulduklarında içeri aktarma kitaplığını DLL'e örtük olarak bağlamak yürütülebilir.  
  
 MFC'nin MFCx0.DLL'den işlevleri ve sınıfları dışarı aktarmak için .def dosyası kullandığını unutmayın.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarmak](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C dili yürütülebilir öğelerinde kullanmak için C++ işlevlerini dışarı aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C veya C++ dili yürütülebilir öğelerinde kullanmak için C işlevlerini dışarı aktarma](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Hangi dışarı aktarma yöntemini kullanacağınızı belirleme](../build/determining-which-exporting-method-to-use.md)  
  
-   [__Declspec(dllimport) kullanarak bir uygulama içeri aktarmak için](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL başlatma](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [.def dosyaları](../build/reference/module-definition-dot-def-files.md)  
  
-   [Modül tanımlama deyimleri kuralları](../build/reference/rules-for-module-definition-statements.md)  
  
-   [Düzenlenmiş adlar](../build/reference/decorated-names.md)  
  
-   [İçeri ve dışarı aktarma satır içi işlevler](../build/importing-and-exporting-inline-functions.md)  
  
-   [Karşılıklı içeri aktarmalar](../build/mutual-imports.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)