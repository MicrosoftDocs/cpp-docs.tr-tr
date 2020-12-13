---
description: 'Hakkında daha fazla bilgi edinin: engelleme of yığın çekişmesi'
title: Engelleme yığın çakışması
ms.date: 11/04/2016
helpviewer_keywords:
- heap contention
ms.assetid: 797129d7-5f8c-4b0e-8974-bb93217e9ab5
ms.openlocfilehash: c58849bee46dd0d870d1067f17581429339fbc0e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142577"
---
# <a name="avoidance-of-heap-contention"></a>Engelleme yığın çakışması

MFC ve ATL tarafından sunulan varsayılan dize yöneticileri, genel yığının en üstünde basit sarmalayıcılardır. Bu genel yığın tamamen iş parçacığı açısından güvenlidir, yani birden çok iş parçacığının yığını bozmadan aynı anda bellekten ayırabileceği ve serbest bir şekilde boşaltılacağı anlamına gelir. İş parçacığı güvenliği sağlamaya yardımcı olmak için yığının kendine erişimi seri hale getirmek gerekir. Bu genellikle kritik bir bölüm veya benzer kilitleme mekanizmasıyla gerçekleştirilir. İki iş parçacığı yığına aynı anda erişmeyi denediğinde, diğer iş parçacığının isteği bitene kadar bir iş parçacığı engellenir. Birçok uygulama için bu durum nadiren oluşur ve yığının kilitleme mekanizmanın performans etkisi göz ardı edilir. Ancak, yığın kilidi için birden çok iş parçacığından oluşan yığına sıklıkla erişen uygulamalar, uygulamanın tek iş parçacıklı (birden çok CPU içeren makinelerde bile) daha yavaş çalışmasına neden olabilir.

[CStringT](../atl-mfc-shared/reference/cstringt-class.md) kullanan uygulamalar özellikle yığın çekişmesine açıktır, çünkü nesneler üzerindeki işlemler `CStringT` genellikle dize arabelleğinin yeniden tahsisat gerektirmektedir.

İş parçacıkları arasındaki yığın çekişmesini sağlamanın bir yolu, her bir iş parçacığının özel, iş parçacığı yerel yığınından dizeler ayırmasını kullanmaktır. Belirli bir iş parçacığının ayırıcısı ile ayrılan dizelerin yalnızca o iş parçacığında kullanıldığı sürece, ayırıcı iş parçacığı açısından güvenli olmamalıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, kendi özel iş parçacığı dışı güvenli yığınını, bu iş parçacığında dizeler için kullanılmak üzere ayıran bir iş parçacığı yordamı gösterilmektedir:

[!code-cpp[NVC_ATLMFC_Utilities#182](../atl-mfc-shared/codesnippet/cpp/avoidance-of-heap-contention_1.cpp)]

## <a name="comments"></a>Yorumlar

Aynı iş parçacığı yordamı kullanılarak birden çok iş parçacığı çalışıyor olabilir, ancak her iş parçacığı kendi yığınına sahip olduğundan iş parçacıkları arasında çekişme yoktur. Ayrıca, her yığının iş parçacığı açısından güvenli olmaması aslında iş parçacığının yalnızca bir kopyası çalışıyor olsa bile performans açısından ölçülebilir bir artış sağlar. Bu, öbekten, eşzamanlı erişime karşı koruma sağlamak için pahalı bir kilitleme işlemleri kullanmayan bir sonucudur.

Daha karmaşık bir iş parçacığı yordamı için iş parçacığı yerel depolama (TLS) yuvasında iş parçacığının dize yöneticisine bir işaretçi depolamak uygun olabilir. Bu, iş parçacığının dize yöneticisine erişmek için iş parçacığı yordamı tarafından çağrılan diğer işlevlere izin verir.

## <a name="see-also"></a>Ayrıca bkz.

[CStringT ile bellek yönetimi](../atl-mfc-shared/memory-management-with-cstringt.md)
