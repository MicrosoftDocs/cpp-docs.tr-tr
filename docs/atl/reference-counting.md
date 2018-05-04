---
title: Başvuru (ATL) sayım | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1ba27f00bf25f88575101b1299daf50f94000ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="reference-counting"></a>Başvuru sayımı
COM kendisi, nesne artık kullanılmayan düşündüğünde nesneyi bellekten kaldırmak otomatik olarak denemez. Bunun yerine, nesne Programcı kullanılmayan nesne kaldırmanız gerekir. Programcı nesneyi dayalı olarak bir başvuru sayısı kaldırılmış olup olmadığını belirler.  
  
 COM kullanır **IUnknown** yöntemleri [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) ve [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317), bir nesne üzerinde arabirimleri başvurusu sayısı yönetmek için. Bu yöntemleri çağırmak için genel kurallar şunlardır:  
  
-   Bir istemci bir arabirim işaretçisi aldığı zaman `AddRef` arabirimde çağrılmalıdır.  
  
-   İstemci arabirimi işaretçisi kullanılarak bitirdi her çağırmalısınız **sürüm**.  
  
 Basit bir uygulamada her `AddRef` çağrısı artırır ve her **sürüm** nesne içinde bir sayaç değişken azaltır çağırın. Sayısı sıfır olarak geri döndüğünde, arabirimi artık tüm kullanıcılar var ve kendisini bellekten kaldırmak ücretsizdir.  
  
 Böylece her nesneye (değil tek bir arabirim) referansı sayılan başvuru sayımı da uygulanabilir. Bu durumda, her `AddRef` ve **sürüm** nesnesinde merkezi uygulamasına temsilciler çağırın ve **sürüm** başvuru sayısı sıfır ulaştığında nesnenin tamamı boşaltır.  
  
> [!NOTE]
>  Zaman bir `CComObject`-türetilen nesne kullanılarak yapılandırılmıştır **yeni** işleci, başvuru sayısı: 0. Bu nedenle, yapılan bir çağrı `AddRef` başarıyla oluşturduktan sonra yapılması gerektiğini `CComObject`-türetilmiş bir nesne içermelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM giriş](../atl/introduction-to-com.md)   
 [Başvuru sayımı yoluyla nesne yaşam süresi yönetme](http://msdn.microsoft.com/library/windows/desktop/ms687260)

