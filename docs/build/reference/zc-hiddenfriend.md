---
title: '/Zc: hiddenFriend (Standart C++ gizli arkadaş kurallarını zorla)'
description: 'Uyumlu veya gevşek gizli arkadaş uyumluluğu için Microsoft C++/Zc: hiddenFriend derleyici seçeneği hakkında bilgi edinin.'
ms.date: 01/23/2021
f1_keywords:
- /Zc:hiddenFriend
helpviewer_keywords:
- /Zc:hiddenFriend
- Zc:hiddenFriend
- -Zc:hiddenFriend
ms.openlocfilehash: 5a3487cc4899cf6a07e91dc5ce5b7cd8f8784737
ms.sourcegitcommit: 74e58bee5cffb30b66e17be6dbfde2544369638e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2021
ms.locfileid: "98766839"
---
# <a name="zchiddenfriend-enforce-standard-c-hidden-friend-rules"></a>`/Zc:hiddenFriend` (Standart C++ gizli arkadaş kurallarını zorla)

Derleyicinin gizli arkadaş işlevlerinin veya işlev şablonlarının C++ standart işleme uygun olduğunu belirtir.

## <a name="syntax"></a>Syntax

> **`/Zc:hiddenFriend`**\[**`-`**]

## <a name="remarks"></a>Açıklamalar

**`/Zc:hiddenFriend`** Seçeneği, seçenek davranışının bir alt kümesini sunar [`/permissive-`](permissive-standards-conformance.md) . Derleyicinin gizli arkadaşlar için standart ile uyumlu olduğunu söyler. Derleyici yalnızca [bağımsız değişkene bağlı arama](../../cpp/argument-dependent-name-koenig-lookup-on-functions.md) (adl) içindeki gizli arkadaşları, kapsayan sınıf türünün açık örnekleri veya şablon parametreleri için içerir. Kısıtlama, bir tür üzerinde işlemleri örtük Dönüştürmelere uygulamadan korumak için gizli arkadaşları kullanmanıza olanak sağlar. Bu seçenek, alternatif olarak kullanabilecek koddaki derleme hızını iyileştirebilir [`/permissive-`](permissive-standards-conformance.md) .

*Gizli arkadaş* , **`friend`** yalnızca bir sınıf veya sınıf şablonu tanımı içinde tanımlanmış bir işlev veya işlev şablonudur. Varsayılan olarak, Microsoft C++ derleyicisi gizli arkadaş bildirimlerini, her yerde aşırı yükleme çözümlemesi için aday olarak kaldırmaz. Bu eski davranış, gizli arkadaş işlevlerini daha fazla bağlamdaki olası adaylar olarak ekleyerek derleyicinin yavaşlamasına neden olabilir.

Standart C++ gizli arkadaş davranışı altında varsayılan olarak etkindir **`/permissive-`** . Seçenek belirtildiğinde eski gizli arkadaş davranışını belirtmek için **`/permissive-`** kullanın **`/Zc:hiddenFriend-`** . C++ 20 modüllerinin kullanılması, standart gizli arkadaş davranışı gerektirir.

Bu **`/Zc:hiddenFriend`** seçenek, Visual Studio 2019 sürüm 16,4 ' den itibaren kullanılabilir.

Belirttiğinizde derleyici davranışı örnekleri için **`/Zc:hiddenFriend`** bkz. [gizli arkadaş adı arama kuralları](./permissive-standards-conformance.md#hidden-friend-name-lookup-rules).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini, veya içerecek şekilde *`/Zc:hiddenFriend`* değiştirin *`/Zc:hiddenFriend-`* ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[`/Zc` Uyumsuzlu](zc-conformance.md)\
[`/permissive-`](permissive-standards-conformance.md)
