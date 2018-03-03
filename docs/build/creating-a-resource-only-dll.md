---
title: "Yalnızca kaynak DLL oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd65085c9a0ecc0479c7d22feb5587d1e94447de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-resource-only-dll"></a>Yalnızca Kaynak DLL Oluşturma  
  
Yalnızca kaynak DLL simgeler, bit eşlemler, dizeler ve iletişim kutuları gibi kaynakları içeren bir DLL'dir. Yalnızca kaynak DLL kullanarak aynı kümesini kaynakları birden çok programlar arasında paylaşmak için iyi bir yöntemidir. Ayrıca uygulamanın birden çok dil için yerelleştirilmiş kaynaklar sağlamak için en iyi yolu olan (bkz [MFC uygulamalarında yerelleştirilmiş kaynaklar: Uydu DLL'leri](../build/localized-resources-in-mfc-applications-satellite-dlls.md)).  
  
Yalnızca kaynak DLL oluşturmak için yeni bir Win32 DLL (MFC olmayan) projesi oluşturun ve kaynaklarınızı projeye ekleyin.  
  
-   Win32 projedeki seçin **yeni proje** iletişim kutusuna ve Win32 Proje Sihirbazı'nda bir DLL proje türünü belirtin.  
  
-   DLL için kaynakları (örneğin, bir dize veya menü) içeren yeni bir kaynak betik oluşturun ve .rc dosyasını kaydedin.  
  
-   Üzerinde **proje** menüsünde tıklatın **varolan öğeyi Ekle**ve ardından yeni .rc dosyası projeye ekleyin.  
  
-   Belirtin [/NOENTRY](../build/reference/noentry-no-entry-point.md) bağlayıcı seçeneği. / NOENTRY bağlayıcı başvuru bağlama engeller `_main` DLL'e; yalnızca kaynak DLL oluşturmak için bu seçeneği gereklidir.  
  
-   Dll dosyasını oluşturun.  
  
Yalnızca kaynak DLL kullanan uygulama çağrısı [LoadLibrary](../build/loadlibrary-and-afxloadlibrary.md) DLL'ye açıkça bağlanmak için. Kaynaklara erişmek için genel işlevlerini `FindResource` ve `LoadResource`, hangi iş her türlü kaynak veya aşağıdaki kaynak özgü işlevleri birini arayın:  
  
-   `FormatMessage`  
  
-   `LoadAccelerators`  
  
-   `LoadBitmap`  
  
-   `LoadCursor`  
  
-   `LoadIcon`  
  
-   `LoadMenu`  
  
-   `LoadString`  
  
Uygulama çağırmalıdır `FreeLibrary` onu bittiğinde kaynakları kullanarak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
  
[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)  
[Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)