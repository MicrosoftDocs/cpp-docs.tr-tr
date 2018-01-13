---
title: "__Declspec(dllexport) kullanarak DLL'den dışarı aktarma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- dllexport
- __declspec
dev_langs: C++
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- names [C++], DLL exports by
- export directives [C++]
- exporting DLLs [C++], __declspec(dllexport) keyword
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51f20e47724a6d32dad014fbaf025cd283112c54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exporting-from-a-dll-using-declspecdllexport"></a>__declspec(dllexport) Kullanarak DLL'den Dışarı Aktarma
Sunulan Microsoft **__declspec(dllexport)** dışarı aktarma adlarını otomatik olarak oluşturmak ve bunları bir .lib dosyasında yerleştirmek derleyici izin vermek için Visual C++ 16 bit derleyici sürümünde. Bu .lib dosya daha sonra yalnızca statik .lib gibi DLL ile bağlamak için kullanılabilir.  
  
 Yeni derleyici sürümler, verileri, İşlevler, sınıfları veya sınıf üyesi işlevleri kullanarak bir DLL dışa aktarabilirsiniz **__declspec(dllexport)** anahtar sözcüğü. **__declspec(dllexport)** .def dosyası kullanmanız gerekmez nesne dosyasına dışa aktarma yönergesi ekler.  
  
 Dışarı aktarmaya çalışırken C++ işlevi adlar durumunda bu kolaylık en çok görünür olur. Ad düzenlemesi için standart bir belirtim olduğundan, dışarı aktarılan bir işlevin adını derleyici sürümler arasında değişebilir. Kullanırsanız **__declspec(dllexport)**, DLL ve bağımlı .exe dosyaları yeniden derlenmesi için adlandırma kuralı değişiklikleri yalnızca hesabına gerekli.  
  
 Çoğu, sıra numaraları, NONAME ve özel, yalnızca .def dosyası yapılabilir ve bu öznitelikler .def dosyası olmadan belirtmek için bir yolu yoktur gibi dışarı aktarma yönergeleri. Ancak, kullanarak **__declspec(dllexport)** bir .def kullanmanın yanı sıra dosya derleme hataları neden olmaz.  
  
 İşlevleri dışarı aktarmak için **__declspec(dllexport)** bir anahtar sözcük belirtilmişse, anahtar sözcüğü arama kuralı anahtar sözcüğünü sola görünmelidir. Örneğin:  
  
```  
__declspec(dllexport) void __cdecl Function1(void);  
```  
  
 Tüm bir sınıf üyesi işlevleri ve genel veri üyelerini dışarı aktarmak için anahtar sözcüğü sınıf adının solundaki aşağıdaki gibi görünmelidir:  
  
```  
class __declspec(dllexport) CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
> [!NOTE]
>  `__declspec(dllexport)`bir işlev uygulanamaz `__clrcall` çağırma.  
  
 DLL dosyanızı oluştururken, genellikle işlev prototipleri ve/veya veriyorsanız ve ekleme sınıfları içeren bir üst bilgi dosyası oluştur **__declspec(dllexport)** üstbilgi dosyası bildirimler için. Kodunuzu daha okunabilir hale getirmek için makro tanımlamak **__declspec(dllexport)** ve verdiğiniz her simgesiyle makrosu kullanın:  
  
```  
#define DllExport   __declspec( dllexport )   
```  
  
 **__declspec(dllexport)** depoları işlev adları DLL'nin dışarı aktarma. Tablonun boyutu en iyi hale getirmek istiyorsanız bkz [dışarı aktarma işlevleri DLL'den tarafından sıra yerine ada göre](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
> [!NOTE]
>  DLL kaynak kodundan Win16 Win32 bağlantı noktası oluşturma, her bir örneğini değiştirmek **__declspec(dllexport)** ile **__declspec(dllexport)**.  
  
 Bir başvuru olarak Win32 Winbase.h üstbilgi dosyası içinde arayın. Örnekleri içeren **__declspec(dllimport)** kullanımı.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [.Def dosyaları kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarmak](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C dili yürütülebilir öğelerinde kullanmak için C++ işlevlerini dışarı aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C veya C++ dili yürütülebilir öğelerinde kullanmak için C işlevlerini dışarı aktarma](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Hangi dışarı aktarma yöntemini kullanacağınızı belirleme](../build/determining-which-exporting-method-to-use.md)  
  
-   [__Declspec(dllimport) kullanarak bir uygulama içeri aktarmak için](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL başlatma](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [__Declspec anahtar sözcüğü](../cpp/declspec.md)  
  
-   [İçeri ve dışarı aktarma satır içi işlevler](../build/importing-and-exporting-inline-functions.md)  
  
-   [Karşılıklı içeri aktarmalar](../build/mutual-imports.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)