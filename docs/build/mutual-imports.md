---
title: Karşılıklı içeri aktarmalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b43977f86be409698d8fbdba16fc63d85acfac5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="mutual-imports"></a>Karşılıklı İçeri Aktarmalar
Aktarımlar karşılıklı (veya döngüsel) olduğunda veya başka bir yürütülebilir dosyaya verme zorluklar gösterir. Örneğin, iki DLL simgeleri birbirinden, karşılıklı özyinelemeli işlevler için benzer içeri aktarın.  
  
 Birbirini yürütülebilir dosyaları (genellikle DLL'ler) alma hiçbiri diğer ilk oluşturmadan oluşturulabilir, bir sorundur. Her oluşturma işlemi giriş olarak bir derleme süreci tarafından üretilen bir içeri aktarma kitaplığını gerektirir.  
  
 Çözüm yürütülebilir dosyayı oluşturmadan içeri aktarma kitaplığı üreten/DEF seçeneği ile LIB yardımcı programını kullanmaktır. Bu yardımcı programı kullanarak, ihtiyacınız olan tüm içeri aktarma kitaplıkları oluşturabilir olsun kaç DLL'leri oynayan veya nasıl karmaşık bağımlılıklar.  
  
 Karşılıklı içeri aktarmalar işlemek için genel çözüm şöyledir:  
  
1.  Her DLL'i sırayla alın. (Bazı sıralar daha uygun olsa da herhangi bir sırada, uygulanabilirdir.) Tüm gerekli içeri aktarma kitaplıkları var ve geçerli, yürütülebilir dosya (DLL) oluşturmak için bağlantı çalıştırmak istiyorsanız. Bu, bir içeri aktarma kitaplığı oluşturur. Aksi takdirde içeri aktarma kitaplığı üretmek için LIB çalıştırın.  
  
     / DEF seçeneği ile LIB çalıştırma üreten bir ek dosyası ile bir. EXP uzantısı. . EXP dosya daha sonra çalıştırılabilir dosyayı oluşturmak için kullanılmalıdır.  
  
2.  Bütün içeri aktarma kitaplıkları oluşturmak için bağlantı veya LIB kullandıktan sonra geri dönün ve önceki adımda oluşturulan değil tüm yürütülebilir dosyaları oluşturmak için bağlantı çalıştırın. LINK satırında karşılık gelen .exp dosyası belirtilmelidir unutmayın.  
  
     Daha önce bir içeri aktarma kitaplığını DLL1 için LIB yardımcı programını çalıştırırsanız, LIB DLL1.exp dosyasını üretilen. DLL1.dlll oluştururken, giriş bağlantı olarak DLL1.exp kullanmalısınız.  
  
 Aşağıdaki çizimde bir çözüm iki Karşılıklı içeri aktarma dll, DLL1 ve DLL2 gösterir. Adım 1/DEF seçeneği ayarlanmış DLL1 LIB, çalıştırmaktır. 1. adım DLL1.lib, içeri aktarma kitaplığı ve DLL1.exp'yi oluşturur. 2. adımda içeri aktarma kitaplığını içeri aktarma kitaplığı DLL2'in sembolleri sırayla üreten DLL2 oluşturmak için kullanılır. 3. adım DLL1.exp ve DLL2.lib Giriş olarak kullanarak DLL1 oluşturur. DLL2'in içeri aktarma kitaplığını oluşturmak için LIB kullanılmadığından DLL2 .exp dosyasının gerekli olmadığını unutmayın.  
  
 ![Karşılıklı içeri aktarmalar iki DLL bağlantı kullanmayı](../build/media/vc37yj1.gif "vc37YJ1")  
Karşılıklı içeri aktarmalar ile iki DLL'leri bağlama  
  
## <a name="limitations-of-afxext"></a>_AFXEXT Sınırlamaları  
 Kullanabileceğiniz `_AFXEXT` , MFC uzantı DLL'leri MFC uzantı DLL'leri çok katmanlı olmayan sürece önişlemci simgesi. MFC uzantı DLL'leri çağıran veya kendi MFC uzantı sonra MFC sınıflarından, DLL'leri sınıflarda öğesinden türetilen varsa, Karışıklığı önlemek için kendi önişlemci sembolü kullanmanız gerekir.  
  
 Söz konusu Win32 sorunudur, herhangi bir veri olarak açıkça bildirmelidir **__declspec(dllexport)** DLL'den dışarı aktarılacak ise ve **__declspec(dllimport)** DLL'den dışarı aktarılacak ise. Tanımladığınızda `_AFXEXT`, MFC üstbilgileri olduğundan emin olun **AFX_EXT_CLASS** doğru tanımlanmadı.  
  
 Olduğunda, birden çok katman, bir sembol gibi **AFX_EXT_CLASS** MFC uzantı DLL'si yeni sınıfları dışarı aktarma yanı sıra çünkü diğer sınıfları başka bir MFC uzantı DLL içeri aktarma yeterli değildir. Bu sorunu çözmek için DLL'i kullanmak DLL kendisini oluşturduğunuzu gösteren özel bir önişlemci sembolü kullanın. Örneğin, iki MFC uzantı DLL'leri, A.dll ve B.dll düşünün. Her A.h ve B.h'taki bazı sınıflarda sırasıyla verin. B.dll a.DLL'den sınıfları kullanır. Üstbilgi dosyaları şunun gibi görünür:  
  
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
  
 A.dll oluşturulduğunda ile oluşturulmuştur `/D A_IMPL` ve B.dll oluşturulduğunda ile yerleşiktir `/D B_IMPL`. Her bir DLL için ayrı sembol kullanarak `CExampleB` aktarılır ve `CExampleA` b.dll oluşturulduğunda alınır. `CExampleA` a.dll oluşturulurken dışarı ve içeri B.dll (veya başka bir istemci) tarafından kullanıldığında.  
  
 Bu tür katmanlama yerleşik kullanırken yapılamaz **AFX_EXT_CLASS** ve `_AFXEXT` önişlemci simgeleri. Yukarıda açıklanan teknikleri MFC'nin etkin teknolojileri, veritabanı ve ağ MFC uzantı DLL'leri oluştururken düzeneğini bir şekilde benzemeyen bu sorunu çözer.  
  
## <a name="not-exporting-the-entire-class"></a>Bütün sınıfı dışa değil  
 Sınıfının tümüne dışarı aktarma değil, MFC makroları tarafından oluşturulan tüm gerekli veri öğelerinin doğru verildiğinden emin olmanız gerekir. Bu tanımlayarak yapılabilir `AFX_DATA` belirli sınıfınızın makrosu için. Bu, bütün sınıfı dışarı aktarma değil dilediğiniz zaman yapılmalıdır.  
  
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
  
-   [DLL'den dışarı aktarma](../build/exporting-from-a-dll.md)  
  
-   [Kullanarak bir DLL dışarı aktarın. DEF dosyaları](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarmak](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C dili yürütülebilir öğelerinde kullanmak için C++ işlevlerini dışarı aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Hangi dışarı aktarma yöntemini kullanacağınızı belirleme](../build/determining-which-exporting-method-to-use.md)  
  
-   [__Declspec(dllimport) kullanarak bir uygulama içeri aktarmak için](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [LIB yardımcı programını ve/DEF seçeneği](../build/reference/lib-reference.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İçeri ve Dışarı Aktarma](../build/importing-and-exporting.md)