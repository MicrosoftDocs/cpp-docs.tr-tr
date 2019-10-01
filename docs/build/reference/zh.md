---
title: /ZH (hata ayıklama bilgilerinde dosya sağlama toplamı hesaplamasına yönelik karma algoritma)
description: Hata ayıklama bilgilerinde MD5, SHA-1 veya SHA-256 kaynak dosya toplamlarını etkinleştirmek için/ZH derleyici seçeneğini kullanın
ms.date: 09/16/2019
f1_keywords:
- /ZH
- /ZH:MD5
- /ZH:SHA1
- /ZH:SHA_256
helpviewer_keywords:
- /ZH
- /ZH:MD5
- /ZH:SHA1
- /ZH:SHA_256
- /ZH compiler option
- /ZH:MD5 compiler option
- /ZH:SHA1 compiler option
- /ZH:SHA_256 compiler option
- Hash algorithm for file checksum in debug info
ms.openlocfilehash: f05dc2bc3b8ce4502ff16a6e19fdbb10763b34ba
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71686875"
---
# <a name="zh-hash-algorithm-for-calculation-of-file-checksum-in-debug-info"></a>/ZH (hata ayıklama bilgilerinde dosya sağlama toplamı hesaplamasına yönelik karma algoritma)

Her kaynak dosyanın sağlama toplamını oluşturmak için kullanılacak şifreleme karma algoritmasını belirtir.

## <a name="syntax"></a>Sözdizimi

> **/Zh:** {**MD5**|**SHA1**|**SHA_256**}

## <a name="arguments"></a>Bağımsız Değişkenler

**/Zh: MD5**\
Sağlama toplamı için bir MD5 karması kullanın. Bu seçenek varsayılandır.

**/Zh: SHA1**\
Sağlama toplamı için SHA-1 karması kullanın.

**/Zh: SHA_256**\
Sağlama toplamı için bir SHA-256 karması kullanın.

## <a name="remarks"></a>Açıklamalar

PDB dosyaları, ilişkili çalıştırılabilirteki nesne koduna derlenen her kaynak dosya için bir sağlama toplamı depolar. Sağlama toplamı, hata ayıklayıcının, yüklediği kaynak kodun çalıştırılabilirle eşleştiğini doğrulamasına izin verir. Derleyici ve hata ayıklayıcı MD5, SHA-1 ve SHA-256 karma algoritmalarını destekler. Varsayılan olarak, derleyici sağlama toplamını oluşturmak için bir MD5 karması kullanır. Bu seçeneği **/zh: MD5** seçeneğini kullanarak açıkça belirtebilirsiniz.

MD5 ve SHA-1 ' deki sorunların çakışmasıyla ilgili bir risk nedeniyle, Microsoft **/zh: SHA_256** seçeneğini kullanmanızı önerir. SHA-256 karması, derleme süreleriyle küçük bir artış oluşmasına neden olabilir.

Birden fazla **/zh** seçeneği belirtildiğinde, son seçenek kullanılır.

**/Zh** seçeneği, Visual Studio 2019 sürüm 16,4 ' den itibaren kullanılabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında bu derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. Yapılandırma açılan **öğesini** **Tüm yapılandırmalara**ayarlayın.

1. @No__t-1**C/C++**  > **komut satırı** özellik sayfasını **yapılandırma özellikleri**' ni seçin.

1. **Ek seçenekler** özelliğini bir **/zh: MD5**, **/zh: SHA1**veya **/zh: SHA_256** seçeneğini ekleyecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici seçenekleri](compiler-options.md)\
[Kaynak sunucu](/windows/win32/debug/source-server-and-source-indexing)
