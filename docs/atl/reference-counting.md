---
title: Referans Sayma (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
ms.openlocfilehash: 095f0ad2ecc1e1a870077899d61a3c594f8cc95f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321737"
---
# <a name="reference-counting"></a>Referans Sayma

COM kendisi, nesnenin artık kullanılmadığını düşündüğünde bir nesneyi bellekten otomatik olarak kaldırmaya çalışmaz. Bunun yerine, nesne programcısı kullanılmayan nesneyi kaldırmalıdır. Programcı, bir nesnenin başvuru sayısına göre kaldırılıp kaldırılamayacağına karar vetır.

`IUnknown` COM, bir nesneüzerindeki arabirimlerin başvuru sayısını yönetmek için [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)yöntemlerini kullanır. Bu yöntemleri çağırmak için genel kurallar şunlardır:

- Bir istemci bir arabirim `AddRef` işaretçisi aldığında, arabirimde çağrılmalıdır.

- İstemci arabirim işaretçisini kullanmayı bitirdiğinde, 'yi aramalı. `Release`

Basit bir uygulamada, `AddRef` her çağrı artışları `Release` ve her çağrı nesneiçinde bir sayaç değişkeni kararver. Sayım sıfıra döndüğünde, arabirimartık kullanıcı içermez ve kendisini bellekten kaldırmakta özgürdür.

Başvuru sayımı, nesneye yapılan her başvurunun (tek bir arabirime değil) sayılması için de uygulanabilir. Bu durumda, `AddRef` her `Release` ve nesne üzerinde merkezi bir uygulamaya `Release` delegeleri çağırın ve başvuru sayısı sıfıra ulaştığında tüm nesneyi serbest.

> [!NOTE]
> Yeni `CComObject` **işleç** kullanılarak türetilmiş bir nesne oluşturulduğunda, başvuru sayısı 0'dır. Bu nedenle, `AddRef` başarılı bir şekilde `CComObject`türetilen nesne oluşturulduktan sonra bir çağrı yapılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[COM'a Giriş](../atl/introduction-to-com.md)<br/>
[Başvuru Sayımı yoluyla Nesne Yaşam Ömürlerini Yönetme](/windows/win32/com/managing-object-lifetimes-through-reference-counting)
