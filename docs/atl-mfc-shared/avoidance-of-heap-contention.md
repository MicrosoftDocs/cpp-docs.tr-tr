---
title: Yığın çekişmesini engelleme
ms.date: 11/04/2016
helpviewer_keywords:
- heap contention
ms.assetid: 797129d7-5f8c-4b0e-8974-bb93217e9ab5
ms.openlocfilehash: 45510607a63759aad9444959716bef164eda1492
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743272"
---
# <a name="avoidance-of-heap-contention"></a>Yığın çekişmesini engelleme

MFC ve ATL tarafından sağlanan varsayılan dize yöneticileri genel bir yığın üzerinde basit sarmalayıcıları ' dir. Bu genel bir öbek tam olarak birden çok iş parçacığı ayırmak ve yığın bozulmasını olmadan aynı anda bellekten, ücretsiz anlamına gelir, güvenlidir. İş parçacığı güvenliği sağlamak için kendisine erişim serileştirmek yığın vardır. Bu genellikle bir kritik bölüm veya benzer kilitleme mekanizması ile gerçekleştirilir. Her iki iş parçacığı yığın bağlayıp buna erişim denediğinizde, diğer iş parçacığının istek işlemi tamamlanana kadar bir iş parçacığı engellenir. Birçok uygulama için yığının kilitleme mekanizması performans etkisini göz ardı edilebilir ve bu durum nadiren oluşur. Ancak, sık sık yığın birden fazla iş parçacığından erişen uygulamalar için yığının kilit çakışması ve uygulamanın tek iş parçacıklı (bile makinelerinde birden çok CPU ile), göre daha yavaş çalışmasına neden olabilir.

Kullanan uygulamalar [CStringT](../atl-mfc-shared/reference/cstringt-class.md) yığın çekişmesini özellikle açıktır çünkü işlemleri `CStringT` nesneler sık dize arabelleğinin reallocation gerektirir.

Yığın çekişmesini iş parçacıkları arasında hafifletmek yollarından biri, her bir iş parçacığı bir özel, iş parçacığı-yerel yığından dizeleri ayırmak olmasını sağlamaktır. Dizeler ile ayrılmış olduğu sürece bir belirli iş parçacığının ayırıcı, yalnızca bu iş parçacığındaki kullanılıyorsa, ayırıcı iş parçacığı açısından güvenli olması gerekmez.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, iş parçacığı üzerinde dizeleri kullanmak için kendi özel iş parçacığı güvenli olmayan yığın ayıran bir iş parçacığı yordamı gösterilmektedir:

[!code-cpp[NVC_ATLMFC_Utilities#182](../atl-mfc-shared/codesnippet/cpp/avoidance-of-heap-contention_1.cpp)]

## <a name="comments"></a>Açıklamalar

Bu iş parçacığı yordamı kullanarak birden çok iş parçacığı çalışıyor olabilir, ancak her iş parçacığının kendi yığın olduğundan iş parçacıkları arasında hiçbir çakışma yok. Ayrıca, yalnızca bir kopyasını iş parçacığı çalışıyor olsa bile her yığın iş parçacığı açısından güvenli değildir olgu ölçülebilir bir performans artışı sağlar. Bu pahalı bir birbirine kenetlenmiş işlemler eşzamanlı erişime karşı korumak için kullanmayan yığın sonucudur.

Daha karmaşık bir iş parçacığı yordamı için iş parçacığının dize Yöneticisi için bir işaretçi bir iş parçacığı yerel depolama (TLS) yuvasında depolamak kullanışlı olabilir. Bu iş parçacığının dize Yöneticisi'ne erişmek için iş parçacığı yordamı tarafından çağrılan diğer işlevler sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[CStringT ile Bellek Yönetimi](../atl-mfc-shared/memory-management-with-cstringt.md)
