---
description: 'Daha fazla bilgi edinin: başvuru sayımı'
title: Başvuru sayımı (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
ms.openlocfilehash: 0e80986f530d1d0c79fd5c271eb21e292dec06de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165751"
---
# <a name="reference-counting"></a>Başvuru sayımı

COM 'un kendisi, nesnenin artık kullanılmıyor olduğunu düşündüğü zaman bir nesneyi bellekten kaldırmayı otomatik olarak denemez. Bunun yerine, nesne programlayıcı kullanılmamış nesneyi kaldırmalıdır. Programcı, bir nesnenin bir başvuru sayısına göre kaldırılıp kaldırılamayacağını belirler.

COM, `IUnknown` bir nesnedeki arabirimlerin başvuru sayısını yönetmek için, [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)yöntemlerini kullanır. Bu yöntemleri çağırmak için genel kurallar şunlardır:

- Bir istemci bir arabirim işaretçisi aldığında `AddRef` arabirim üzerinde çağrılmalıdır.

- İstemci, arabirim işaretçisini kullanmayı bitirdiğinde, çağrısı gerekir `Release` .

Basit bir uygulamada her bir çağrı `AddRef` artar ve her bir `Release` çağrı nesnenin içindeki bir sayaç değişkenini azaltır. Sayı sıfıra döndüğünde, arabirimin artık kullanıcıları yoktur ve kendisini bellekten kaldırmak ücretsizdir.

Başvuru sayımı, nesneye yapılan her başvurunun (tek bir arabirime değil) sayılmasını sağlamak için de uygulanabilir. Bu durumda, her `AddRef` ve `Release` çağrısı nesnesi üzerinde merkezi bir uygulamaya temsilci atar ve `Release` başvuru sayısı sıfıra ulaştığında tüm nesneyi serbest bırakır.

> [!NOTE]
> Türetilmiş bir `CComObject` nesne işleci kullanılarak oluşturulduğunda **`new`** , başvuru sayısı 0 ' dır. Bu nedenle, `AddRef` ile türetilmiş nesne başarıyla oluşturulduktan sonra bir çağrısı yapılmalıdır `CComObject` .

## <a name="see-also"></a>Ayrıca bkz.

[COM'a Giriş](../atl/introduction-to-com.md)<br/>
[Başvuru sayımı aracılığıyla nesne ömrünü yönetme](/windows/win32/com/managing-object-lifetimes-through-reference-counting)
