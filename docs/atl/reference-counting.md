---
title: Başvuru sayım (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
ms.openlocfilehash: fa160cb40af632321e1b14fd3ca88a4dd578b972
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62249658"
---
# <a name="reference-counting"></a>Başvuru sayımı

COM kendisi, nesnenin artık kullanılıp kullanılmadığını düşündüğünde nesneyi bellekten kaldırmak otomatik olarak denemez. Bunun yerine, nesne Programcı kullanılmayan nesne kaldırmanız gerekir. Programcı, nesnenin başvuru sayısının göre kaldırılıp kaldırılamayacağını belirler.

COM kullanan `IUnknown` yöntemleri [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) ve [yayın](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), arabirimleri bir nesnede başvuru sayısını yönetme. Bu yöntemleri çağırmak için genel kurallar şunlardır:

- Her bir istemci bir arabirim işaretçisini aldığında `AddRef` arabiriminde çağrılmalıdır.

- Arabirim işaretçisi kullanılarak istemci bitirdi her çağırmalıdır `Release`.

Basit bir uygulamada her `AddRef` artırır ve her çağrı `Release` nesnesinin içindeki bir sayaç değişkeni azaltır çağırın. Sayısı sıfıra döndürüldüğünde arabirimi artık tüm kullanıcıları içeren ve kendisini bellekten kaldırmak ücretsizdir.

Böylece her nesneye (değil tek bir arabirim) başvuru sayılan başvuru sayımı de uygulanabilir. Bu durumda, her `AddRef` ve `Release` temsilciler merkezi bir uygulamaya nesne üzerinde arama ve `Release` , başvuru sayısı sıfır ulaştığında tüm nesneyi serbest bırakır.

> [!NOTE]
>  Olduğunda bir `CComObject`-türetilmiş nesnesi kullanılarak oluşturulduğunda **yeni** işleci, başvuru sayısı: 0. Bu nedenle, bir çağrı `AddRef` başarıyla oluşturduktan sonra yapılması gerektiğini `CComObject`-türetilmiş bir nesneye.

## <a name="see-also"></a>Ayrıca bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[Başvuru sayımı yoluyla, nesne kullanım ömrü Yönetimi](/windows/desktop/com/managing-object-lifetimes-through-reference-counting)
