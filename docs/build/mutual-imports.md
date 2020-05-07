---
title: Karşılıklı İçeri Aktarmalar
ms.date: 11/04/2016
helpviewer_keywords:
- mutual DLL imports [C++]
- AFX_DATA
- importing DLLs [C++], mutual imports
- mutually importing executable files [C++]
- AFX_EXT_CLASS macro
- circular imports
- _AFXEXT preprocessor symbol
- DLLs [C++], importing
- executable files [C++], importing
- extension DLLs [C++], mutual imports
- exporting DLLs [C++], mutual imports
ms.assetid: 2cc29537-92ee-4d92-af39-8b8b3afd808f
ms.openlocfilehash: f01e69138a6ca1744645a1c2fa8525b7088e260d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295681"
---
# <a name="mutual-imports"></a>Karşılıklı İçeri Aktarmalar

İçeri aktarmalar karşılıklı (veya dairesel) olduğunda, başka bir yürütülebilir dosyaya dışarı veya içeri aktarmak karmaşıklıkları gösterir. Örneğin, iki DLL, birbirini karşılıklı özyinelemeli işlevlere benzer şekilde, sembolleri birbirinden içe aktarır.

Birlikte kullanılamayan yürütülebilir dosyaları (genellikle dll 'Ler) ile ilgili sorun, hiçbir bir kez oluşturmadan derlenmez. Her yapı işlemi, diğer yapı işlemi tarafından oluşturulan bir içeri aktarma kitaplığı olan giriş olarak gerektirir.

Çözüm, yürütülebilir dosya oluşturmadan bir içeri aktarma kitaplığı üreten/DEF seçeneğiyle LIB yardımcı programını kullanmaktır. Bu yardımcı programı kullanarak, ihtiyacınız olan tüm içeri aktarma kitaplıklarını, kaç dll 'nin dahil olduğunu veya bağımlılıkların ne kadar karmaşık olduğunu bağımsız olarak oluşturabilirsiniz.

Karşılıklı içeri aktarmaları işlemek için genel çözüm şunlardır:

1. Her DLL 'yi sırayla alın. (Herhangi bir sıralama uygulanabilir olsa da, bazı siparişler daha uygun olur.) Gerekli tüm içeri aktarma kitaplıkları varsa ve geçerli ise, çalıştırılabilir dosyayı (DLL) derlemek için bağlantıyı çalıştırın. Bu bir içeri aktarma kitaplığı oluşturur. Aksi takdirde, bir içeri aktarma kitaplığı oluşturmak için LIB ' i çalıştırın.

   LıB komutunu/DEF seçeneğiyle çalıştırmak, ile ek bir dosya oluşturur. EXP uzantısı. İçin. Daha sonra yürütülebilir dosyayı derlemek için EXP dosyasının kullanılması gerekir.

1. Tüm içeri aktarma kitaplıklarını derlemek için bağlantı veya LıB kullandıktan sonra, önceki adımda oluşturulmamış yürütülebilir dosyaları derlemek için geri dönün ve bağlantıyı çalıştırın. BAĞLANTı satırında karşılık gelen. exp dosyasının belirtilmesi gerektiğini unutmayın.

   DLL1 için bir içeri aktarma kitaplığı oluşturmak üzere daha önce LıB yardımcı programını çalıştırırsanız LIB, DLL1. exp dosyasını da üreten. DLL1. dlll derlerken bağlantı kurmak için DLL1. exp 'yi giriş olarak kullanmanız gerekir.

Aşağıdaki çizimde, iki karşılıklı içeri aktarma dll, DLL1 ve DLL2 için bir çözüm gösterilmektedir. 1. adım, DLL1 üzerinde/DEF seçenek kümesiyle LIB komutunu kullanmaktır. 1. adım DLL1. lib, bir içeri aktarma kitaplığı ve DLL1. exp üretir. 2. adımda içeri aktarma kitaplığı, DLL2's sembolleri için içeri aktarma kitaplığı üreten DLL2 oluşturmak için kullanılır. 3. adım, DLL1. exp ve DLL2. lib kullanarak girdi olarak DLL1 oluşturur. LıB, DLL2's içeri aktarma kitaplığı derlemek için kullanılmadığından, DLL2 için bir. exp dosyası gerekli değildir.

(media/vc37yj1.gif "İki DLL 'yi bağlamak için karşılıklı içeri aktarmaları kullanarak") ![iki DLL 'yi bağlamak için karşılıklı içeri aktarmalar kullanma]<br/>
Iki dll 'yi karşılıklı Içeri aktarmalar ile bağlama

## <a name="limitations-of-_afxext"></a>_AFXEXT sınırlamaları

MFC uzantı dll 'lerinizin ön işlemci sembolünü, `_AFXEXT` bırden çok MFC uzantı dll katmanınız olmadığı sürece kullanabilirsiniz. Kendi MFC uzantı dll 'larınızda bulunan ve daha sonra MFC sınıflarından türeten sınıfları çağıran MFC uzantı dll 'Leri varsa, karışıklığı önlemek için kendi önişlemci sembolünü kullanmanız gerekir.

Bu sorun, Win32 'de, bir DLL 'den içeri aktarıldıysa **__declspec (dllexport)** olarak açıkça bir veri bildirmeniz ve bir dll 'den içeri aktarılacaksa **__declspec (dllimport)** olması gerekir. Tanımladığınızda `_AFXEXT`, MFC başlıkları **AFX_EXT_CLASS** doğru tanımlandığından emin olur.

Birden çok katmanınız olduğunda, bir MFC uzantı DLL 'SI yeni sınıfları dışarı aktarabileceğinden ve başka bir MFC uzantısı DLL 'sinden başka sınıfları içeri aktarabileceğinden, **AFX_EXT_CLASS** gibi bir sembol yeterli değildir. Bu sorunu çözmek için dll 'yi kullanarak DLL 'nin kendisini oluşturduğunuzu belirten özel bir ön işlemci sembolünü kullanın. Örneğin, bir. dll ve B. dll olmak üzere iki MFC uzantı dll 'si düşünün. Her biri, sırasıyla bir. h ve B. h içindeki bazı sınıfları dışa aktarır. B. dll, bir. dll dosyasından sınıfları kullanır. Üst bilgi dosyaları şuna benzer:

```
/* A.H */
#ifdef A_IMPL
   #define CLASS_DECL_A   __declspec(dllexport)
#else
   #define CLASS_DECL_A   __declspec(dllimport)
#endif

class CLASS_DECL_A CExampleA : public CObject
{ ... class definition ... };

// B.H
#ifdef B_IMPL
   #define CLASS_DECL_B   __declspec(dllexport)
#else
   #define CLASS_DECL_B   __declspec(dllimport)
#endif

class CLASS_DECL_B CExampleB : public CExampleA
{ ... class definition ... };
...
```

Bir. dll oluşturulduğunda, ile `/D A_IMPL` oluşturulur ve B. dll oluşturulduğunda, ile `/D B_IMPL`oluşturulur. Her DLL için ayrı semboller kullanarak, `CExampleB` B. dll oluşturulurken `CExampleA` içeri aktarılır ve içeri aktarılır. `CExampleA`, bir. dll oluşturulduğunda ve B. dll (veya başka bir istemci) tarafından kullanıldığında içeri aktarılır.

Yerleşik **AFX_EXT_CLASS** ve `_AFXEXT` önişlemci sembolleri kullanılırken bu tür katmanlama yapılamaz. Yukarıda açıklanan teknik, MFC 'nin kendi etkin teknolojilerini, veritabanını ve ağ MFC uzantı dll 'Lerini oluştururken kullandığı mekanizmanın aksine bir şekilde bu sorunu çözer.

## <a name="not-exporting-the-entire-class"></a>Sınıfın tamamı dışarı aktarılmıyor

Bir sınıfın tamamını dışa aktardığınızda, MFC makroları tarafından oluşturulan gerekli veri öğelerinin doğru şekilde dışarı aktarıldığından emin olmanız gerekir. Bu, belirli sınıfınızın makrosunu yeniden `AFX_DATA` tanımlayarak yapılabilir. Bu, tüm sınıfı dışarı aktardığınız zaman yapılmalıdır.

Örneğin:

```
/* A.H */
#ifdef A_IMPL
   #define CLASS_DECL_A  _declspec(dllexport)
#else
   #define CLASS_DECL_A  _declspec(dllimport)
#endif

#undef  AFX_DATA
#define AFX_DATA CLASS_DECL_A

class CExampleA : public CObject
{
   DECLARE_DYNAMIC()
   CLASS_DECL_A int SomeFunction();
   //... class definition ...
};

#undef AFX_DATA
#define AFX_DATA
```

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [DLL 'den dışarı aktarma](exporting-from-a-dll.md)

- [Kullanarak DLL 'den dışarı aktarın. DEF dosyaları](exporting-from-a-dll-using-def-files.md)

- [__Declspec (dllexport) kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak dışarı ve içeri aktarma](exporting-and-importing-using-afx-ext-class.md)

- [C Dili Çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Hangi dışarı aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [LIB yardımcı programı ve/DEF seçeneği](reference/lib-reference.md)

## <a name="see-also"></a>Ayrıca bkz.

[İçeri ve Dışarı Aktarma](importing-and-exporting.md)
