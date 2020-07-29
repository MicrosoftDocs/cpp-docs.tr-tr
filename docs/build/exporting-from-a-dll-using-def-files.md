---
title: DEF Dosyaları Kullanarak DLL'den Dışarı Aktarma
ms.date: 05/06/2019
helpviewer_keywords:
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
- exporting DLLs [C++], DEF files
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
ms.openlocfilehash: 8fdbb060502f339eb748306eef582d2f296b1f60
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229837"
---
# <a name="exporting-from-a-dll-using-def-files"></a>DEF Dosyaları Kullanarak DLL'den Dışarı Aktarma

Modül tanımı veya DEF dosyası (*. def), bir DLL 'nin çeşitli özniteliklerini tanımlayan bir veya daha fazla modül deyimi içeren bir metin dosyasıdır. **`__declspec(dllexport)`** DLL 'nin işlevlerini dışarı aktarmak için anahtar sözcüğünü kullanmıyorsanız, dll BIR def dosyası gerektirir.

En az bir DEF dosyası aşağıdaki modül tanımı deyimlerini içermelidir:

- Dosyadaki ilk deyimin LIBRARY deyimleri olması gerekir. Bu ifade, bir DLL 'ye ait olan DEF dosyasını tanımlar. KITAPLıK deyiminden sonra DLL adı gelir. Bağlayıcı bu adı DLL 'nin içeri aktarma kitaplığına koyar.

- Dışarı aktarmalar ifadesinde, DLL tarafından dışarı aktarılan işlevlerin adları ve isteğe bağlı olarak sıralı değerleri listelenir. İşlevin adını bir at işareti (@) ve bir sayı ile izleyerek bir sıra değeri atayabilirsiniz. Sıra değerlerini belirttiğinizde, 1 ile N arasında olmalıdır; burada N, DLL tarafından dışarıya alınan işlevlerin sayısıdır. İşlevleri sıralı olarak dışa aktarmak istiyorsanız, bkz. [BIR DLL 'Den Işlevleri ada](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) ve bu konu başlığı yerine sıraya göre dışarı aktarma.

Örneğin, bir ikili arama ağacını uygulamak için kodu içeren bir DLL aşağıdaki gibi görünebilir:

```
LIBRARY   BTREE
EXPORTS
   Insert   @1
   Delete   @2
   Member   @3
   Min   @4
```

MFC DLL oluşturmak için [MFC DLL Sihirbazı 'nı](../mfc/reference/mfc-dll-wizard.md) kullanırsanız, sihirbaz sizin için bir Iskelet def dosyası oluşturur ve projenize otomatik olarak ekler. Bu dosyaya aktarılacak işlevlerin adlarını ekleyin. MFC olmayan dll 'Ler için, DEF dosyasını kendiniz oluşturun ve projenize ekleyin. Ardından **Proje**  >  **özellikleri**  >  **bağlayıcı**  >  **giriş**  >  **Modülü tanım dosyası** ' na gidin ve def dosyasının adını girin. Her yapılandırma ve platform için bu adımı tekrarlayın veya **yapılandırma = tüm yapılandırmalar**ve **Platform = tüm platformlar**' ı seçerek tümünü bir kez yapın.

Bir C++ dosyasındaki işlevleri dışarı aktarıyorsanız, birlikte bulunan adları DEF dosyasına yerleştirmeniz veya dışarı aktarılan işlevlerinizi extern "C" kullanarak standart C bağlantısıyla tanımlamanız gerekir. Düzenlenmiş adları DEF dosyasına yerleştirmeniz gerekiyorsa, bunları [dumpbin](../build/reference/dumpbin-reference.md) aracını kullanarak veya bağlayıcı [/map](../build/reference/map-generate-mapfile.md) seçeneğini kullanarak elde edebilirsiniz. Derleyici tarafından üretilen düzenlenmiş adların derleyiciye özgü olduğunu unutmayın. Microsoft C++ derleyicisi (MSVC) tarafından üretilen düzenlenmiş adları bir DEF dosyasına yerleştirirseniz, DLL 'nize bağlanan uygulamaların aynı MSVC sürümü kullanılarak oluşturulması gerekir; böylece, çağıran uygulamadaki düzenlenmiş adların DLL 'nin DEF dosyasındaki adı verdiğiniz adlarla eşleşmesi gerekir.

> [!NOTE]
> Visual Studio 2015 ile oluşturulmuş bir DLL, Visual Studio 2017 ya da Visual Studio 2019 ile oluşturulmuş uygulamalar tarafından tüketilebilir.

[Uzantı DLL 'si](../build/extension-dlls-overview.md)oluşturuyorsanız ve bir def dosyası kullanarak dışarı aktarıyorsanız, dışa aktarılan sınıfları içeren üst bilgi dosyalarınızın başına ve sonuna aşağıdaki kodu yerleştirin:

```
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

Bu satırlar, dahili olarak kullanılan veya sınıflarınıza eklenen MFC değişkenlerinin MFC uzantı DLL 'nizden içeri aktarılmasını (veya içe aktarılmasını) sağlar. Örneğin, kullanarak bir sınıfı türettiğinde `DECLARE_DYNAMIC` ,, `CRuntimeClass` sınıfınıza üye değişkeni eklemek için makro genişletilir. Bu dört satırı bırakmak, DLL 'nizin yanlış bir şekilde derlenmesi veya bağlantı oluşturmasına ya da istemci uygulaması DLL 'ye bağlasa hata oluşmasına neden olabilir.

DLL derlerken bağlayıcı, bir dışa aktarma (. exp) dosyası ve bir içeri aktarma kitaplığı (. lib) dosyası oluşturmak için DEF dosyasını kullanır. Bağlayıcı daha sonra DLL dosyasını oluşturmak için dışarı aktarma dosyasını kullanır. DLL 'ye örtük olarak bağlanan ve derleme sırasında içeri aktarma kitaplığına bağlantı veren yürütülebilir dosyalar.

MFC 'nin işlevleri ve sınıfları MFCx0.dll dışarı aktarmak için DEF dosyaları kullandığını unutmayın.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [__Declspec (dllexport) kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak dışarı ve içeri aktarma](exporting-and-importing-using-afx-ext-class.md)

- [C Dili Çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C veya C++ Dili Çalıştırılabilirlerinde kullanmak için C işlevlerini dışarı aktarma](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Hangi dışarı aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 'yi başlatma](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [. def dosyaları](reference/module-definition-dot-def-files.md)

- [Modül tanımlama deyimleri kuralları](reference/rules-for-module-definition-statements.md)

- [Düzenlenmiş adlar](reference/decorated-names.md)

- [Satır içi işlevleri içeri ve dışarı aktarma](importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](mutual-imports.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](exporting-from-a-dll.md)
