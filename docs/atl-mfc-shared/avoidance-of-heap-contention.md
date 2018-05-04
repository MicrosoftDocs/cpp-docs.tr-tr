---
title: Yığın Çekişme kaçınma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- heap contention
ms.assetid: 797129d7-5f8c-4b0e-8974-bb93217e9ab5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 731fcb2328f789e5c487dc56510bbd6f7ec049ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="avoidance-of-heap-contention"></a>Yığın Çekişme kaçınma
MFC ve ATL tarafından sağlanan varsayılan dize yöneticileri, genel bir öbek üzerinde basit sarmalayıcıları kullanıcılardır. Bu genel yığın tam olarak birden çok iş parçacığı ayırın ve aynı anda öbek bozulmasını olmadan bellekten bunu serbest anlamına iş parçacığı, ' dir. İş parçacığı güvenliğini sağlamaya yardımcı olmak için kendisine erişim serileştirmek yığın sahiptir. Bu genellikle bir kritik bölüm veya benzer kilitleme mekanizması olarak gerçekleştirilir. İki iş parçacığı öbek aynı anda erişmeye her bir iş parçacığı diğer iş parçacığı isteği tamamlanana kadar engellendi. Birçok uygulama için öbek 's kilitleme mekanizması performans etkisini önemsizdir ve bu durum nadiren oluşur. Ancak, birden çok iş parçacığından öbek sık sık eriştiği uygulamalar için öbek 's kilit çakışması ve uygulamanın tek iş parçacıklı (makinelerde bile birden çok CPU ile), daha yavaş çalışmasına neden olabilir.  
  
 Kullanan uygulamalar [CStringT](../atl-mfc-shared/reference/cstringt-class.md) yığın Çekişme özellikle açıktır çünkü işlemleri `CStringT` nesneler sık dize arabellek yeniden ayırma gerektirir.  
  
 İş parçacıkları arasında yığın Çekişme hafifletmek için bir yol, bir özel, iş parçacığı yerel yığınından dizeleri tahsis her iş parçacığı sağlamaktır. Dizeleri ile ayrılan sürece bir belirli iş parçacığının ayırıcısı yalnızca o iş parçacığı kullanılan, ayırıcı iş parçacığı açısından güvenli olması gerekmez.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, iş parçacığı dizeleri kullanılmak üzere kendi özel iş parçacığı güvenli olmayan yığın ayırır bir iş parçacığı yordamı gösterir:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#182](../atl-mfc-shared/codesnippet/cpp/avoidance-of-heap-contention_1.cpp)]  
  
## <a name="comments"></a>Açıklamalar  
 Bu aynı iş parçacığı yordamı kullanarak birden çok iş parçacığı çalışıyor olabilecek ancak her iş parçacığının kendi yığın olduğundan iş parçacıkları arasında hiçbir Çekişme yoktur. Ayrıca, iş parçacığı tek kopyası çalışıyor olsa bile her yığın iş parçacığı açısından güvenli değil olgu performans ölçülebilir bir artış sağlar. Pahalı birbirine kenetlenmiş işlemler eşzamanlı erişime karşı korumak için kullanmayan yığın sonucudur.  
  
 Daha karmaşık bir iş parçacığı yordamı için iş parçacığının dizesi yöneticisi için bir işaretçi bir iş parçacığı yerel depolaması (TLS) yuvasına depolamak kullanışlı olabilir. Bu iş parçacığının dize Yöneticisi'ne erişmek için iş parçacığı yordamı tarafından çağrılan diğer işlevler sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStringT ile Bellek Yönetimi](../atl-mfc-shared/memory-management-with-cstringt.md)

