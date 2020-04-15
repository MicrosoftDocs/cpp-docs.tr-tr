---
title: Uzaktan Yapı Etkinlikleri (Linux C++)
ms.date: 06/07/2019
ms.assetid: 165d3690-5bd8-4b0b-bc66-8b699d85a61b
ms.openlocfilehash: 4a3e9019d4dacc3d494feb5d6de8f5c2247e4d12
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "79441503"
---
# <a name="build-event-properties-linux-c"></a>Etkinlik Özellikleri Oluşturma (Linux C++)

::: moniker range="vs-2015"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="pre-build-event"></a>Ön Yapı Etkinliği

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Önceden yapı olay aracının çalışması için bir komut satırı belirtir. |
| Açıklama | Önceden yapı olay aracının görüntülenmesi için bir açıklama belirtir. |
| Yapı'da Kullanım | Bu yapı olayının geçerli yapılandırma için yapının dışında kalıp kalmayacağını belirtir. |
| Kopyalanması gereken ek dosyalar | Uzak sisteme kopyalanması için ek dosyalar belirtir. İsteğe bağlı olarak, bunun gibi bir sözdizimini kullanarak yerel den uzak eşleme çiftleri belirtin: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2, yerel bir dosyanın uzak sistemde belirtilen uzak konuma kopyalanabileceği. |

## <a name="pre-link-event"></a>Ön Bağlantı Etkinliği

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Ön bağlantı olay aracının çalışması için bir komut satırı belirtir. |
| Açıklama | Ön bağlantı olay aracının görüntülenmesi için bir açıklama belirtir. |
| Yapı'da Kullanım | Bu yapı olayının geçerli yapılandırma için yapının dışında kalıp kalmayacağını belirtir. |
| Kopyalanması gereken ek dosyalar | Uzak sisteme kopyalanması için ek dosyalar belirtir. İsteğe bağlı olarak, bunun gibi bir sözdizimini kullanarak yerel den uzak eşleme çiftleri belirtin: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2, yerel bir dosyanın uzak sistemde belirtilen uzak konuma kopyalanabileceği. |

## <a name="post-build-event"></a>Yapı Sonrası Etkinlik

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Yapı sonrası olay aracının çalışması için bir komut satırı belirtir. |
| Açıklama | Yapı sonrası olay aracının görüntülenmesi için bir açıklama belirtir. |
| Yapı'da Kullanım | Bu yapı olayının geçerli yapılandırma için yapının dışında kalıp kalmayacağını belirtir. |
| Kopyalanması gereken ek dosyalar | Uzak sisteme kopyalanması için ek dosyalar belirtir. İsteğe bağlı olarak, bunun gibi bir sözdizimini kullanarak yerel den uzak eşleme çiftleri belirtin: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2, yerel bir dosyanın uzak sistemde belirtilen uzak konuma kopyalanabileceği. |

## <a name="remote-pre-build-event"></a>Uzaktan Ön Yapı Etkinliği

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Önceden inşa edilen olay aracının uzak sistemde çalışması için bir komut satırı belirtir. |
| Açıklama | Önceden yapı olay aracının görüntülenmesi için bir açıklama belirtir. |
| Yapı'da Kullanım | Bu yapı olayının geçerli yapılandırma için yapının dışında kalıp kalmayacağını belirtir. |
| Kopyalanması gereken ek dosyalar | Uzak sistemden kopyalanması gereken ek dosyaları belirtir. İsteğe bağlı olarak, bunun gibi bir sözdizimini kullanarak yerel eşleme çiftleri için uzaktan belirtin: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2, uzak bir dosyayerel makinede belirtilen konuma kopyalanabilir. |

## <a name="remote-pre-link-event"></a>Uzaktan Ön Bağlantı Etkinliği

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Ön bağlantı olay aracının uzak sistemde çalışması için bir komut satırı belirtir. |
| Açıklama | Ön bağlantı olay aracının görüntülenmesi için bir açıklama belirtir. |
| Yapı'da Kullanım | Bu yapı olayının geçerli yapılandırma için yapının dışında kalıp kalmayacağını belirtir. |
| Kopyalanması gereken ek dosyalar | Uzak sistemden kopyalanması gereken ek dosyaları belirtir. İsteğe bağlı olarak, bunun gibi bir sözdizimini kullanarak yerel eşleme çiftleri için uzaktan belirtin: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2, uzak bir dosyayerel makinede belirtilen konuma kopyalanabilir. |

## <a name="remote-post-build-event"></a>Uzaktan Post-Build Etkinliği

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Yapı sonrası olay aracının uzak sistemde çalışması için bir komut satırı belirtir. |
| Açıklama | Yapı sonrası olay aracının görüntülenmesi için bir açıklama belirtir. |
| Yapı'da Kullanım | Bu yapı olayının geçerli yapılandırma için yapının dışında kalıp kalmayacağını belirtir. |
| Kopyalanması gereken ek dosyalar | Uzak sistemden kopyalanması gereken ek dosyaları belirtir. İsteğe bağlı olarak, bunun gibi bir sözdizimini kullanarak yerel eşleme çiftleri için uzaktan belirtin: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2, uzak bir dosyayerel makinede belirtilen konuma kopyalanabilir. |

::: moniker-end
