---
title: "Statik kitaplıklar (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 02/03/2017
ms.prod: windows-client-threshold
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a68475447ed520298b0eab7949386c2e8d078ac6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="static-libraries-ccx"></a>Statik kitaplıklar (C + +/ CX)
Evrensel Windows platformu uygulamasında kullanılan bir statik kitaplık STL türleri ve evrensel Windows platformu uygulama platformundan dışarıda Win32 API çağrıları dahil olmak üzere, ISO-standart C++ kodu içerebilir. Bir statik kitaplık Windows çalışma zamanı bileşenleri kullanır ve Windows çalışma zamanı bileşenleri bazı sınırlamalarla birlikte oluşturabilir.  
  
## <a name="creating-static-libraries"></a>Statik kitaplıklar oluşturma  
  
#### <a name="to-create-a-static-library-for-use-in-a-universal-windows-platform-app"></a>Evrensel Windows platformu uygulamasında kullanmak için bir statik kitaplık oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya** > **yeni** > **proje** > **boş statik kitaplık** Evrensel Windows platformu uygulamaları.  
  
2.  İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**. İçinde **özellikleri** iletişim kutusundaki **yapılandırma özellikleri** > **genel** sayfasında, kümesine Evrensel Windows platformu uygulama destek  **Evet**.  
  
3.  Üzerinde **yapılandırma özellikleri** > **C/C++** sayfasında **Tüket** Windows çalışma zamanı **uzantısı** için**(/ZW) Evet**.  
  
 Evrensel Windows platformu uygulamaları için hariç tutulan bir Win32 API çağrısı yaparsanız, yeni bir statik kitaplık derlerken derleyici hatası C3861, "tanımlayıcısı bulunamadı." Yükselt Windows çalışma zamanı için desteklenen alternatif bir yöntem aramak için bkz: [Windows API'larını Windows mağazası uygulamalarında alternatifleri](http://msdn.microsoft.com/en-us/75568012-61e0-41cc-a4df-c698f54f21ec).  
  
 Bir evrensel Windows platformu uygulama çözüme C++ statik kitaplık projesi eklerseniz, böylece Evrensel Windows platformu desteği özelliğini ayarlamak kitaplık projenin özellik ayarlarını güncelleştirmek zorunda kalabilirsiniz **Evet**. Bu ayar olmadan kodunu oluşturur ve bağlantılar, ancak bir hata oluşur uygulama için doğrulamaya [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)]. Statik lib içereceği tükettiği proje aynı derleyici ayarları ile derlenmiş.  
  
 Ortak oluşturur statik bir kitaplığı kullanacak varsa `ref` sınıfları, ortak arabirimi sınıfları veya ortak değeri sınıfları, bu uyarıyı bağlayıcı başlatır:  
  
> **LNK4264 Uyarı:** /ZW ile statik bir kitaplık içine; derlenen nesne dosya arşivleme Windows çalışma zamanı türleri yazarken Windows çalışma zamanı meta verileri içeren bir statik kitaplık ile bağlamak için Önerilmemesine olduğunu unutmayın.  
  
 Yalnızca statik kitaplık kitaplığı dışında tüketilen Windows çalışma zamanı bileşenleri üretmez uyarı güvenle yoksayabilirsiniz. Kitaplığı tanımlayan bir bileşeni kullanacak değil, türü bilgileri ortak meta veriler içeriyor olsa bile ardından bağlayıcı hemen uygulama en iyi duruma getirebilirsiniz. Bu bir statik kitaplık ortak bileşenlerinde derlenir ancak çalışma zamanında etkinleşir değil anlamına gelir. Bu nedenle, bir dinamik bağlantı kitaplığı (DLL) tüketim için amaçlanmıştır herhangi bir Windows çalışma zamanı bileşenin başka bileşenler veya uygulamalar tarafından uygulanmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş parçacığı oluşturma ve hazırlama](../cppcx/threading-and-marshaling-c-cx.md)