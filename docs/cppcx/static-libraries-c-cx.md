---
title: "Statik kitaplıklar (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dcd69fc00a44bdc0d8259a4a21d31c83ee5c6258
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="static-libraries-ccx"></a>Statik kitaplıklar (C + +/ CX)
Bir evrensel Windows Platformu (UWP) uygulamasında kullanılan bir statik kitaplık STL türleri ve Windows çalışma zamanı uygulama platformundan dışarıda Win32 API çağrıları dahil olmak üzere, ISO-standart C++ kodu içerebilir. Bir statik kitaplık Windows çalışma zamanı bileşenleri kullanır ve Windows çalışma zamanı bileşenleri bazı sınırlamalarla birlikte oluşturabilir.  
  
## <a name="creating-static-libraries"></a>Statik kitaplıklar oluşturma  
  
#### <a name="to-create-a-static-library-for-use-in-a-uwp-app"></a>Bir statik kitaplık kullanmak için bir UWP uygulaması oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya** > **yeni** > **proje**. Altında **Visual C++** > **Windows Evrensel** seçin **statik kitaplık (Evrensel Windows)**.  
  
2.  İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**. İçinde **özellikleri** iletişim kutusundaki **yapılandırma özellikleri** > **C/C++** sayfasında **Windows çalışma zamanı uzantısıkullanma** için **(/ZW) Evet**.  
  
 UWP uygulamalar için hariç tutulan bir Win32 API çağrısı yaparsanız, yeni bir statik kitaplık derlerken derleyici hatası C3861, "tanımlayıcısı bulunamadı." Yükselt Windows çalışma zamanı için desteklenen alternatif bir yöntem aramak için bkz: [UWP uygulamaları Windows API'leri alternatifleri](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).  
  
 Bir UWP uygulaması çözüme C++ statik kitaplık projesi eklerseniz, UWP desteği özelliğini ayarlamak kitaplık projenin özellik ayarları güncelleştirmeye olabilir **Evet**. Bu ayar olmadan kodunu oluşturur ve bağlantılar, ancak bir hata durumunda uygulama için Microsoft Store doğrulamaya oluşur. Statik lib içereceği tükettiği proje aynı derleyici ayarları ile derlenmiş.  
  
 Ortak oluşturur statik bir kitaplığı kullanacak varsa `ref` sınıfları, ortak arabirimi sınıfları veya ortak değeri sınıfları, bu uyarıyı bağlayıcı başlatır:  
  
> **LNK4264 Uyarı:** /ZW ile statik bir kitaplık içine; derlenen nesne dosya arşivleme Windows çalışma zamanı türleri yazarken Windows çalışma zamanı meta verileri içeren bir statik kitaplık ile bağlamak için Önerilmemesine olduğunu unutmayın.  
  
 Yalnızca statik kitaplık kitaplığı dışında tüketilen Windows çalışma zamanı bileşenleri üretmez uyarı güvenle yoksayabilirsiniz. Kitaplığı tanımlayan bir bileşeni kullanacak değil, türü bilgileri ortak meta veriler içeriyor olsa bile ardından bağlayıcı hemen uygulama en iyi duruma getirebilirsiniz. Bu bir statik kitaplık ortak bileşenlerinde derlenir ancak çalışma zamanında etkinleşir değil anlamına gelir. Bu nedenle, bir dinamik bağlantı kitaplığı (DLL) tüketim için amaçlanmıştır herhangi bir Windows çalışma zamanı bileşenin başka bileşenler veya uygulamalar tarafından uygulanmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş parçacığı oluşturma ve hazırlama](../cppcx/threading-and-marshaling-c-cx.md)