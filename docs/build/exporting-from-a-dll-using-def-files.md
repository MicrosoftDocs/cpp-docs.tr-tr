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
ms.openlocfilehash: 22bcca929d687ef3b10ee65bcb2230c03bfb0a11
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706010"
---
# <a name="exporting-from-a-dll-using-def-files"></a>DEF Dosyaları Kullanarak DLL'den Dışarı Aktarma

Bir modül-tanımlama (.def) dosyası, bir DLL'nin çeşitli özniteliklerini tanımlayan bir veya daha fazla modül deyimi içeren bir metin dosyasıdır. Kullanmıyorsanız, **__declspec(dllexport)** DLL işlevlerini dışa aktarmak için anahtar sözcüğü DLL .def dosyası gerektirir.

En az bir .def dosyası aşağıdaki modül tanımlama deyimlerini içermelidir:

- Dosyadaki ilk deyim LIBRARY deyimi olmalıdır. Bu ifade, .def dosyanın DLL'ye ait olarak tanımlar. LIBRARY deyimini DLL'in adı tarafından izlenir. Bağlayıcı, bu adı DLL'in içe aktarma kitaplığına yerleştirir.

- EXPORTS deyimi, ad ve isteğe bağlı olarak DLL tarafından dışarı aktarılan işlevlerin sıralı değerlerini listeler. İşlev adının takip ederek sıralı bir değer atadığınız işlevi bir at işareti (@) ve bir sayı. Sıralı değerleri belirttiğinizde, burada N DLL'in dışarı aktardığı işlev sayısı olan N-1 aralığında olmalıdır. Sıralı olarak işlevleri dışarı aktarmak istiyorsanız, bkz. [DLL'den işlevleri yerine ada göre bir DLL](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) bu konuda yanı sıra.

Örneğin, ikili arama ağacını uygulayan bir kod içeren DLL aşağıdakine benzeyebilir:

```
LIBRARY   BTREE
EXPORTS
   Insert   @1
   Delete   @2
   Member   @3
   Min   @4
```

Kullanırsanız [MFC DLL Sihirbazı](../mfc/reference/mfc-dll-wizard.md) MFC DLL'yi oluşturmak için sihirbaz sizin için iskelet .def dosyasını oluşturur ve projenize otomatik olarak ekler. Bu dosyaya dışa aktarılacak işlevlerin adlarını ekleyin. MFC dışı DLL'ler için .def dosyasını kendiniz oluşturmalı ve projenize eklemeniz gerekir.

C++ dosyasındaki işlevleri dışa aktarıyorsanız, düzenlenmiş adları .def dosyasına yerleştirmeniz veya extern "C"'ı kullanarak dışa aktarılan işlevlerinizi standart C bağlantısıyla tanımlamanız gerekir. Düzenlenmiş adları .def dosyasına koymanız gerekiyorsa, bunları kullanarak alabilirsiniz [DUMPBIN](../build/reference/dumpbin-reference.md) aracını veya bağlayıcı [/MAP](../build/reference/map-generate-mapfile.md) seçeneği. Derleyici tarafından üretilen düzenlenmiş adların derleyiciye özel olduğunu unutmayın. Düzenlenmiş adları .def dosyasına Visual C++ derleyicisi tarafından üretilen yerleştirirseniz, bağlanan uygulamalar da böylece uygulamadaki düzenlenmiş adlar DLL'nin .de dışarı aktarılan adların aynı Visual C++ sürümü kullanılarak oluşturulmalıdır f dosyası.

Oluşturuyorsanız bir [uzantı DLL'si](../build/extension-dlls-overview.md), ve bir .def dosyası kullanarak dışa aktarıyorsanız aşağıdaki kodu dışa aktarılan sınıfları içeren üstbilgi dosyalarınızın başında ve sonunda:

```
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

Bu satırlar, içerde kullanılan veya sınıflarınıza eklenen MFC değişkenlerinin olduğundan emin olun verilen (veya içeri aktarılan) MFC uzantısı DLL. Örneğin, kullanarak bir sınıf türetirken `DECLARE_DYNAMIC`, eklemek için makro genişler bir `CRuntimeClass` sınıfınıza üye değişkeni. Bu dört satırı dışarıda bırakmak DLL'NİZİN yanlış derleme veya istemci uygulaması DLL'nize bağlandığında hataya neden neden olabilir.

DLL'yi oluştururken, bağlayıcı dışarı aktarma (.exp) dosyası oluşturmak için .def dosyası ve bir içeri aktarma kitaplık (.lib) dosyası kullanır. Bağlayıcı sonra DLL'i oluşturmak için dışa aktarma dosyası kullanır. Oluşturulduklarında içeri aktarma kitaplığının DLL bağlantısını için örtük olarak bağlama yürütülebilir.

MFC'nin MFCx0.DLL'den işlevleri ve sınıfları dışarı aktarmak için .def dosyası kullandığını unutmayın.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarma](../build/exporting-and-importing-using-afx-ext-class.md)

- [C dili çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C veya C++ dili çalıştırılabilirlerinde kullanmak için C işlevlerini dışa aktarma](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](../build/determining-which-exporting-method-to-use.md)

- [__Declspec(dllimport) kullanarak bir uygulamayı içeri aktarın](../build/importing-into-an-application-using-declspec-dllimport.md)

- [DLL'yi Başlat](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [.def dosyaları](../build/reference/module-definition-dot-def-files.md)

- [Modül tanımlama deyimleri kuralları](../build/reference/rules-for-module-definition-statements.md)

- [Düzenlenmiş adlar](../build/reference/decorated-names.md)

- [İçeri ve dışarı aktarma satır içi işlevler](../build/importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](../build/mutual-imports.md)

## <a name="see-also"></a>Ayrıca Bkz.

[DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)