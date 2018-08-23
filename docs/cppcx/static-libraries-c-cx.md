---
title: Statik kitaplıklar (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5bb69b65d78b6369d872fd6f953f6ddde382c21b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602295"
---
# <a name="static-libraries-ccx"></a>Statik kitaplıklar (C + +/ CX)
Evrensel Windows Platformu (UWP) bir uygulamada kullanılan bir statik kitaplığı STL türleri ve Windows çalışma zamanı uygulama platformdan hariç Win32 API çağrıları dahil olmak üzere, ISO standardı C++ kod içerebilir. Statik kitaplık, Windows çalışma zamanı bileşenlerini kullanır ve Windows çalışma zamanı bileşenleri ile ilgili bazı kısıtlamalar oluşturabilirsiniz.  
  
## <a name="creating-static-libraries"></a>Statik kitaplıklar oluşturma  
  
#### <a name="to-create-a-static-library-for-use-in-a-uwp-app"></a>Bir UWP uygulamasında kullanmak için bir statik kitaplık oluşturmak için  
  
1.  Menü çubuğunda, **dosya** > **yeni** > **proje**. Altında **Visual C++** > **Windows Evrensel** seçin **statik kitaplık (Evrensel Windows)**.  
  
2.  İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**. İçinde **özellikleri** iletişim kutusundaki **yapılandırma özellikleri** > **C/C++** sayfasında **Windows çalışma zamanı uzantısınıkullanma** için **(/ZW) Evet**.  
  
 Yeni bir statik kitaplık için UWP uygulamaları hariç tutulan bir Win32 API çağrısı yapıyorsa derlediğinizde, derleyici hatası C3861, "tanımlayıcısı bulunamadı." oluşturacak Windows çalışma zamanı için desteklenen alternatif bir yöntem aramak için bkz: [UWP uygulamalarında Windows API'lere alternatifler](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).  
  
 Bir UWP uygulaması çözüme bir C++ statik kitaplık projesi eklerseniz, kitaplık projesinin özellik ayarlarını güncelleştirin, böylece UWP desteği özelliği gerekebilir **Evet**. Bu ayar olmadan kod derlenir ve bağlantılar, ancak bir hata için Microsoft Store uygulaması doğrulamaya olduğunda gerçekleşir. Statik kitaplık, projenin kullandığı aynı derleyici ayarları ile derlenmelidir.  
  
 Genel oluşturan bir statik kitaplık kazanabilirsiniz `ref` sınıfları, ortak arabirim sınıfları veya genel değer sınıfları, bağlayıcı bu uyarıyı oluşturur:  
  
> **LNK4264 Uyarı:** statik kitaplığa; /ZW ile derlenen nesne dosyası arşivleme, Windows çalışma zamanı türleri yazılırken, Windows çalışma zamanı meta verileri içeren statik bir kitaplıkla bağlamak için önerilmediğini unutmayın.  
  
 Yalnızca statik kitaplık kitaplık dışında kullanılan Windows çalışma zamanı bileşenleri vermiyor, uyarıyı güvenle yoksayabilirsiniz. Kitaplık tanımlayan bir bileşen kullanmaz, tür bilgilerini ortak meta veriler içeriyor olsa bile ardından bağlayıcı hemen uygulama en iyi duruma getirebilirsiniz. Başka bir deyişle, statik kitaplıkta ortak bileşenler derleyeceği fakat çalışma zamanında etkinleştirmez. Bu nedenle, bir dinamik bağlantı kitaplığı (DLL) tüketim için hazırlanmış herhangi bir Windows çalışma zamanı bileşeni tarafından diğer bileşenler veya uygulamaları uygulanmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş parçacığı oluşturma ve hazırlama](../cppcx/threading-and-marshaling-c-cx.md)