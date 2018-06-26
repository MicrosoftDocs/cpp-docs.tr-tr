---
title: Windows Vista ortak denetimleri için derleme gereksinimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common controls (MFC), build requirements
- common controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f8f167ac560fd8e2109c149f30841ecbe3c44fc8
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930982"
---
# <a name="build-requirements-for-windows-vista-common-controls"></a>Windows Vista Ortak Denetimleri için Derleme Gereksinimleri
Microsoft Foundation Class (MFC) kitaplığı Windows ortak denetimleri sürüm 6.1 destekler. Ortak Denetimler içinde yer alan [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] ve kitaplık dahil [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)]. Kitaplığı, mevcut sınıfları ve yeni sınıflar geliştiren yeni ve destekleyen yöntemleri sağlar [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] ortak denetimler. Uygulamanızı oluşturma sırasında aşağıdaki bölümlerde açıklanan derleme ve Geçiş gereksinimleri karşılamalıdır.  
  
## <a name="compilation-requirements"></a>Derleme gereksinimleri  
  
### <a name="supported-versions"></a>Desteklenen sürümleri  
 Bazı yeni sınıflar ve yöntemler yalnızca Destek [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] ve daha sonra başka yöntemler de önceki işletim sistemlerinde desteklerken. Bir notta `Requirements` her yöntemi konu bölümü belirtir, en düşük işletim sistemi gereklidir [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)].  
  
 Bilgisayarınızı çalışmaz olsa bile [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)], üzerinde çalışacağı bir MFC uygulaması derleme [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] sürüm 6.1 MFC üstbilgi dosyaları bilgisayarınıza varsa. Ancak, ortak için özel tasarlanmış denetimleri [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] yalnızca bu sistemde çalıştırmak ve önceki işletim sistemleri tarafından göz ardı edilir.  
  
### <a name="supported-character-sets"></a>Desteklenen karakter kümeleri  
 Yeni Windows ortak denetimleri yalnızca Unicode karakter kümesini ve ANSI karakter kümesini destekler. Komut satırında uygulamanızı, aşağıdaki tanımla her ikisi de kullanın (/ D) Unicode temel olarak belirtmek için derleyici seçenekleri karakter kümesi:  
  
```  
/D_UNICODE /DUNICODE  
```  
  
 Visual Studio tümleşik geliştirme ortamı (IDE) içinde uygulamanızı belirtebilmeniz **Unicode karakter kümesi** seçeneği **karakter kümesi** özelliğinde **genel**  Proje Özellikleri'nin düğümü.  
  
 MFC için bazı yöntemler ANSI sürümü kullanımdan kaldırıldı Windows ortak denetimleri sürüm 6.1 başlatılıyor. Daha fazla bilgi için bkz: [kullanım dışı ANSI API'ları](../mfc/deprecated-ansi-apis.md).  
  
## <a name="migration-requirements"></a>Geçiş gereksinimleri  
 Windows ortak denetimleri sürüm 6.1 kullanan yeni bir MFC uygulaması oluşturmak için Visual Studio IDE kullanırsanız, IDE uygun bildiriminde otomatik olarak bildirir. Ancak, Visual Studio'nun önceki bir sürümünün varolan bir MFC uygulamasına geçirmek ve yeni ortak denetimleri kullanmak istiyorsanız, IDE otomatik olarak uygulamanızı yükseltmek için bildirim bilgi sağlamaz. Bunun yerine, el ile aşağıdaki kaynak kodunda eklemeniz gerekir, **stdafx.h** dosyası:  
  
```  
#ifdef UNICODE  
#if defined _M_IX86  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='x86' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_IA64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='ia64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_X64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='amd64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#else  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='*' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#endif  
#endif  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel MFC konuları](../mfc/general-mfc-topics.md)   
 [Hiyerarşi grafiği](../mfc/hierarchy-chart.md)   
 [Kullanım Dışı ANSI API'leri](../mfc/deprecated-ansi-apis.md)

