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
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814559"
---
# <a name="mutual-imports"></a>Karşılıklı İçeri Aktarmalar

Imports karşılıklı (veya döngüsel) olduğunda veya başka bir yürütülebilir dosyasına verme zorluklar sunar. Örneğin, iki DLL sembolleri, birbiriyle karşılıklı özyinelemeli işlevler için benzer içeri aktarın.

Yürütülebilir dosyalar (DLL'ler genellikle) birbirini alma ne diğer ilk oluşturmaya gerek kalmadan oluşturulabilir, bir sorundur. Her yapı işlemi giriş olarak bir yapı işlemi tarafından oluşturulan içeri aktarma kitaplığı gerektirir.

Çözüm, yürütülebilir dosyası oluşturmaya gerek kalmadan bir içeri aktarma kitaplığı oluşturur/DEF seçeneği ile LIB yardımcı programını kullanmaktır. Bu yardımcı programını kullanarak, ihtiyacınız olan tüm içeri aktarma kitaplıkları oluşturabilirsiniz ne olursa olsun kaç DLL'leri dahilse veya nasıl karmaşık bağımlılıklar.

Karşılıklı içeri aktarmalar işleme için genel bir çözüm şöyledir:

1. Sırayla her DLL alın. (Bazı siparişler daha iyi olsa herhangi bir sırada, başarılıdır.) Tüm gerekli içeri aktarma kitaplıkları var ve yürütülebilir dosyayı (DLL) oluşturmak için bağlantı çalıştırın. Bu, bir içeri aktarma kitaplığı oluşturur. Aksi takdirde içeri aktarma kitaplığı üretmek için LIB çalıştırın.

   LIB / DEF seçeneği ile çalışan bir ek dosyası üretir bir. EXP uzantısı. . EXP dosya daha sonra yürütülebilir dosyasını oluşturmak için kullanılmalıdır.

1. Tüm içeri aktarma kitaplıkları oluşturmak için bağlantı veya LIB kullandıktan sonra geri dönüp önceki adımda oluşturulan değil tüm yürütülebilir dosyaları oluşturmak için bağlantı çalıştırın. Karşılık gelen .exp dosyası LINK satırında belirtilmelidir unutmayın.

   Daha önce içeri aktarma kitaplığı DLL1 için LIB yardımcı programını çalıştırırsanız, LIB DLL1.exp dosyasını üretilen. DLL1.exp bağlantı giriş olarak DLL1.dlll oluştururken kullanmanız gerekir.

Aşağıdaki çizimde, iki karşılıklı içe aktarma DLL'leri, DLL1 ve DLL2 için bir çözüm gösterilmektedir. Adım 1/DEF seçeneği kümesinde DLL1 ile LIB, çalıştırmaktır. 1. adım DLL1.lib, bir içeri aktarma kitaplığını ve DLL1.exp'yi üretir. 2. adımda içeri aktarma kitaplığını sırayla DLL2'ın sembolleri için bir içeri aktarma kitaplığını oluşturan DLL2 oluşturmak için kullanılır. 3. adım, giriş olarak DLL1.exp'yi ve DLL2.lib'ı kullanarak, DLL1 oluşturur. LIB DLL2'ın içeri aktarma kitaplığı oluşturmak için kullanılamaz olduğundan DLL2 .exp dosyasının gerekli olmadığını unutmayın.

![Karşılıklı içeri aktarmalar iki DLL bağlamak için kullanarak](media/vc37yj1.gif "iki DLL bağlamak için karşılıklı içeri aktarmalar'ı kullanma")<br/>
Karşılıklı içeri aktarmalar ile iki DLL'leri bağlama

## <a name="limitations-of-afxext"></a>_AFXEXT Sınırlamaları

Kullanabileceğiniz `_AFXEXT` MFC uzantısı DLL'leri çözümsüz MFC uzantısı DLL'leri olmayan sürece önişlemci simgesi. MFC uzantı DLL'leri çağrı yapma veya kendi MFC uzantısı DLL'leri sonra MFC sınıflarından türetilen, sınıflar türetilen varsa belirsizlik önlemek için kendi önişlemci sembolü kullanmanız gerekir.

Sorunu söz konusu Win32, tüm veriler olarak açıkça belirtmesi gerekir **__declspec(dllexport)** bir DLL'den dışarı aktarılmasına izin olup olmadığını ve **__declspec(dllimport)** DLL'den içeri aktarılacak ise. Tanımladığınızda `_AFXEXT`, MFC üstbilgi emin **AFX_EXT_CLASS** doğru şekilde tanımlanır.

Olduğunda, birden fazla katman, bir simge gibi **AFX_EXT_CLASS** bir MFC uzantılı DLL yeni sınıfları dışarı aktarma yanı sıra, çünkü diğer sınıfları, başka bir MFC uzantı DLL'SİNDEN içeri aktarma yeterli değildir. Bu sorunu çözmek için DLL kullanan ve DLL kendisi oluşturduğunuzu gösteren özel bir önişlemci sembolü kullanın. Örneğin, iki MFC uzantısı DLL'leri ve A.dll B.dll düşünün. Her bazı sınıflar A.h ve B.h'taki sırasıyla verin. B.dll a.DLL'den sınıfları kullanır. Üst bilgi dosyaları, şunun gibi görünür:

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

A.dll oluşturulduğunda ile oluşturulmuştur `/D A_IMPL` ve B.dll oluşturulduğunda ile oluşturulmuştur `/D B_IMPL`. Her DLL için ayrı bir sembol kullanarak `CExampleB` aktarılır ve `CExampleA` b.dll oluşturulduğunda aktarılır. `CExampleA` a.dll oluşturulurken dışarı ve B.dll (veya başka bir istemci) kullanıldığında içeri aktarılır.

Bu tür katmanlama yerleşik kullanılırken gerçekleştirilemez **AFX_EXT_CLASS** ve `_AFXEXT` önişlemci sembolleri. Yukarıda açıklanan tekniği MFC'nin, etkin teknolojileri, veritabanı ve ağ MFC uzantısı DLL'leri oluştururken kullandığı bir şekilde benzemeyen bu sorunu çözer.

## <a name="not-exporting-the-entire-class"></a>Sınıfın tamamı dışa aktarma değil

Bir sınıfın tamamı dışa aktarma değil, MFC makroları tarafından oluşturulan gerekli veri öğelerinin doğru bir şekilde dışarı aktarıldığından emin olmanız gerekir. Bu tanımlayarak yapılabilir `AFX_DATA` belirli sınıfınızın makro. Bu sınıfın tamamı dışa aktarma değil istediğiniz zaman yapılmalıdır.

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

- [DLL'den dışarı aktarma](exporting-from-a-dll.md)

- [Kullanarak bir DLL dışarı aktarın. DEF dosyaları](exporting-from-a-dll-using-def-files.md)

- [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarma](exporting-and-importing-using-afx-ext-class.md)

- [C dili çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__Declspec(dllimport) kullanarak bir uygulamayı içeri aktarın](importing-into-an-application-using-declspec-dllimport.md)

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [/ DEF seçeneği ve LIB yardımcı programı](reference/lib-reference.md)

## <a name="see-also"></a>Ayrıca bkz.

[İçeri ve Dışarı Aktarma](importing-and-exporting.md)
