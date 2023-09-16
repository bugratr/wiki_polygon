<p align="center">
<img align="center" src="/static/img/polygon-logo.png" width="300">
</p>

<div align="Center">
<h1>0xPolygon Wiki</h1>
<h3>The Value Layer of the Internet</h3>

[![MIT license](https://img.shields.io/badge/License-MIT-blue.svg)](#LICENSE)
[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](https://www.markdownguide.org/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](docs/general/contributing.md)
[![Contributors](https://img.shields.io/github/contributors-anon/0xPolygon/wiki)](https://github.com/0xPolygon/wiki/graphs/contributors)
[![Discord](https://img.shields.io/discord/714888181740339261?color=1C1CE1&label=Polygon%20%7C%20Discord%20%F0%9F%91%8B%20&style=flat-square)](https://discord.com/invite/XvpHAxZ)
[![Twitter](https://img.shields.io/twitter/follow/0xPolygon.svg?style=social)](https://twitter.com/0xPolygon)

</div>

<p align="left">
  The Polygon Wiki serves as the central source of truth for Polygon. Spearheaded by Polygon Labs, 
  it is a community-centric initiative that aims to provide the most current and comprehensive resources for 
  those interested in learning about, developing on, or maintaining projects within the Polygon ecosystem.
</p>

| ❗ Please note that the first half of this README provides an overview of Polygon, while the second half focuses on the repository and source. |
| ---------------------------------------------------------------------------------------------------------------------------------------------- |

<!-- TOC -->

- [Polygon Overview](#polygon-overview)
  * [What is Polygon?](#what-is-polygon-)
    + [Matic Network -> Polygon](#matic-network----polygon)
    + [Polygon 2.0](#polygon-20)
  * [Current Polygon Stack](#current-polygon-stack)
    + [PoS](#pos)
    + [zkEVM](#zkevm)
    + [Supernets](#supernets)
    + [Miden](#miden)
    + [ID](#id)
  * [Proposed Polygon 2.0 Stack](#proposed-polygon-20-stack)
    + [Architecture](#architecture)
      - [1. Staking Layer](#1-staking-layer)
      - [2. Interop Layer](#2-interop-layer)
      - [3. Execution Layer](#3-execution-layer)
      - [4. Proving Layer](#4-proving-layer)
      - [Modular Design](#modular-design)
      - [Future-Proof](#future-proof)
    + [Governance](#governance)
      - [Three Governance Pillars](#three-governance-pillars)
      - [Community Involvement](#community-involvement)
    + [Tokenomics](#tokenomics)
      - [Key Features of POL](#key-features-of-pol)
    + [Evolution of Polygon's Development Frameworks](#evolution-of-polygon-s-development-frameworks)
      - [Framework Comparison](#framework-comparison)
      - [Key Takeaways](#key-takeaways)
  * [Key Polygon Repositories](#key-polygon-repositories)
    + [Polygon 2.0 Repositories under 0xPolygon](#polygon-20-repositories-under-0xpolygon)
    + [zkEVM Repositories under 0xPolygonHermez](#zkevm-repositories-under-0xpolygonhermez)
    + [Polygon PoS Repositories under MaticNetwork](#polygon-pos-repositories-under-maticnetwork)
- [Repository Overview](#repository-overview)
  * [State of the Docs](#state-of-the-docs)
    + [What to Expect?](#what-to-expect-)
  * [Configuration Guide](#configuration-guide)
    + [Static-Site Generator](#static-site-generator)
    + [Deployments](#deployments)
    + [Algolia DocSearch](#algolia-docsearch)
    + [Google Analytics](#google-analytics)
    + [Translations](#translations)
    + [Files and Folders](#files-and-folders)
    + [Priority Labels (`P#`)](#priority-labels---p---)
  * [How to Contribute to the Polygon Wiki](#how-to-contribute-to-the-polygon-wiki)
    + [How to Contribute Changes via the Polygon Wiki Website](#how-to-contribute-changes-via-the-polygon-wiki-website)
    + [How to Locally Run the Polygon Wiki](#how-to-locally-run-the-polygon-wiki)
      - [Setup Steps](#setup-steps)
  * [Primary Maintainers](#primary-maintainers)
  * [License](#license)

<!--/ TOC -->

---

# Polygon Genel Bakış

Bu bölüm, Polygon'un evrimini ve çözüm yığınını kapsamlı bir şekilde tanıtmaktadır. Okuyuculara Polygon'un ne olduğu, stratejik odak alanları gibi Polygon 2.0 ve ekosistemini oluşturan çeşitli bileşenler hakkında net bir anlayış sunmayı amaçlar.

## Polygon Nedir?

Polygon, dijital değer değişimi için evrensel bir katman olarak işlev gören öncü bir blockchain protokolüdür.

### Matic Network -> Polygon

Başlangıçta Ethereum'u bir hibrid Plasma yan zinciri ile ölçeklemeyi amaçlayan Matic Network olarak piyasaya sürülen Polygon, dönüştürücü bir evrim geçirmiştir. Ethereum'un ölçeklenebilirliğini ve çok yönlülüğünü artırmak için tasarlanmış kapsamlı bir çözüm paketine dönüşmüştür. Bu stratejik dönüşüm, çeşitli kullanım durumlarının farklı ihtiyaçlarını ele almayı amaçlayan geniş kapsamlı araştırma ve testlerle desteklenmiştir. Ek olarak, sıfır bilgi teknolojisinin (zk-tech) ortaya çıkışı, blockchain teknolojisinin artık kitlesel benimseme için iyi donanımlı olduğunu gösteren önemli bir dönemeçtir.

Bu çeşitli çözümler bağımsız protokoller olarak var olmamaktadır; bunun yerine, birleşik bir Polygon protokolünün ayrılmaz bileşenleri olarak işlev görmektedirler. Polygon'un yaklaşan sürümü, bu bileşenleri daha da rafine etmeyi ve sorunsuz bir şekilde entegre etmeyi amaçlamaktadır.

### Polygon 2.0

Bu gelişmeler üzerine inşa edilerek, Polygon Labs "Polygon 2.0" adlı, internet için evrensel bir değer katmanı oluşturmayı amaçlayan özel bir protokol tanıtmıştır. Bununla, tümü sorunsuz likidite ile birleştirilmiş Layer 2 çözümlerinin bir ağını birbirine bağlar. Böylece, Polygon 2.0, blockchain teknolojisinin ne başarabileceğinin sınırlarını zorlamayı hedeflemektedir, içerdiği özellikler:

- **Evrensel Blockchain Erişimi**: Blockchain teknolojisine erişimi demokratikleştirir, kitlesel benimseme için yolu açar.
- **Ethereum Uyumu**: Hem ölçeklenebilirliği hem de işlevselliği artırmak için Ethereum'un yol haritasıyla yakından uyum sağlar.
- **Akıcı Likidite**: Çeşitli Katman 2 çözümlerini sorunsuz bir şekilde entegre eden tutarlı bir likidite ekosistemi oluşturur.
- **Etkileşimli Mesajlaşma ve Bileşenlik**: Çeşitli ürün paketleri ve blockchain tabanlı çözümler arasında sorunsuz iletişim ve etkileşim sağlar.
- **Adaptif Modülerlik**: Kolay özelleştirme ve gelecekteki yükseltmeler için esnek bir mimari sağlar.
- **Neredeyse Anlık İşlem Sonuçlanması**: Hızlı ve güvenilir işlem onayları garanti eder, genel kullanıcı deneyimini artırır.

## Güncel Polygon Yığınağı

Bugüne kadar, Polygon çeşitli uygulama ihtiyaçlarını karşılamak üzere tasarlanmış bir ürün ve çözüm yelpazesi sunmaktadır. Aşağıda, mevcut Polygon yığınının ana ürün paketleri yer almaktadır:

### PoS

Kanıta Dayalı Sahiplik (Proof-of-Stake, PoS) ağı, Polygon'un Katman 2 ölçekleme çözümlerinin omurgasını oluşturur. Merkezi olmayan uygulamalar ve işlemler için güvenli ve etkin bir platform sağlar.

### zkEVM

zkEVM, Polygon'un sıfır bilgi temelli Ethereum Sanal Makinesi'dir. Ethereum uyumlu blockhain'lere ölçeklenebilirlik ve gizlilik getirmeyi amaçlar.

### Supernets

Supernets, Polygon Edge konsensus istemcisi üzerinde PolyBFT konsensüsü ile çalışan uygulama özel zincirleridir. Merkezi olmayan uygulamalar için ölçeklenebilirlik ve etkileşimli çalışabilirlik sunarlar.

### Miden

Miden, tamamen EVM-uyumlu bir zk-rollup'tır. Sıfır bilgi kanıtlarının avantajları ile ölçeklenebilir ve güvenli bir Katman 2 çözümü sağlamayı amaçlar.

### ID

Polygon ID, blockchain üzerinde güvenli ve doğrulanabilir kimlik yönetimi sağlamayı amaçlayan merkezi olmayan bir kimlik çözümüdür.

Bu bileşenler topluca, her biri ekosistemin genel ölçeklenebilirliğine, güvenliğine ve etkileşimli çalışabilirliğine katkıda bulunurken belirli ihtiyaçları karşılar şekilde mevcut Polygon yığınını oluşturmaktadır.

## Önerilen Polygon 2.0 Yığınağı

### Mimari

Polygon 2.0, ölçeklenebilirlik, güvenlik ve etkileşimli çalışabilirlik için kapsamlı bir çözüm sağlamak üzere çok katmanlı bir mimari ile tasarlanmıştır. Mimari, dört ana katmandan oluşmaktadır:

#### 1. Staking Katmanı

Staking Katmanı, ağın omurgasını oluşturur ve güvenlik ile konsensus sağlar. Doğrulayıcı yönetimi ve staking operasyonlarından sorumludur, ağın genel bütünlüğünü sağlar.

#### 2. Etkileşimli Çalışabilirlik Katmanı

Interop Katmanı, farklı blockchain ağları arasında sorunsuz iletişimi mümkün kılmaya odaklanır. Çeşitli Katman 2 çözümleri ve hatta diğer Katman 1 blockchain'leri arasında varlık ve veri transferini kolaylaştırmak için LXLY köprüsünü kullanır.

#### 3. Yürütme Katmanı

Bu katman, tüm hesaplamaların gerçekleştiği yerdir. zkEVM, zk-Rollups gibi çeşitli yürütme ortamlarını destekler ve geliştiricilere uygulamaları için en uygun olanı seçme olanağı tanır.

#### 4. Kanıt Katmanı

Kanıt Katmanı, gerçekleştirilen işlemler için kriptografik kanıtlar oluşturmaktan sorumludur. Bu kanıtlar daha sonra işlemleri sonlandırmak için Staking Katmanı tarafından doğrulanır.

Birlikte, bu katmanlar ölçeklenebilir, güvenli ve etkileşimli bir ekosistem sunmak için uyum içinde çalışır, blockchain teknolojisinin başarabileceği sınırları zorlar.

#### Modüler Tasarım

Polygon 2.0'ın modüler yapısı, geliştiricilerin her katmandan farklı bileşenleri bir araya getirmesine olanak tanır, böylece belirli bir uygulama için özelleştirilmiş bir çözüm oluştururlar. Bu modülerlik, konsensus mekanizmaları, yürütme ortamları ve veri erişilebilirlik seçeneklerine de uzanır.

#### Geleceğe Dayanıklı

Polygon 2.0, ortaya çıktıkça yeni teknolojileri entegre etme yeteneği ile geleceğe dayanıklı olarak tasarlanmıştır. Bu, çerçevenin hızla gelişen blockchain manzarasının ön saflarında kalmasını sağlar.

Aşağıdaki diyagram, Polygon 2.0'ın çeşitli katmanlarını göstermektedir.

<p align="center">
<img align="center" src="/static/img/readme/polygon2.0-layers.png" width="900">
</p>

### Yönetişim

Polygon 2.0, topluluğa Polygon ağı üzerinde tam kontrol vermayı amaçlayan ileriye dönük bir merkezi olmayan yönetişim çerçevesi sunar. Bu yönetişim modeli, özellikle Ethereum'unki gibi kanıtlanmış blockchain yönetişim sistemlerinden ilham alır. Çerçeve, üç ana temel üzerine inşa edilmiştir: Protokol Yönetişimi, Sistem Akıllı Sözleşmeleri Yönetişimi ve Topluluk Hazinesi Yönetişimi.

#### Üç Yönetişim Temeli

1. **Protokol Yönetişimi**: Polygon İyileştirme Önerisi (PIP) çerçevesi, Polygon protokollerinin geliştirilmesi için açık bir platform olarak hizmet verir. Polygon 2.0'da, PIP çerçevesi tüm izinsiz yığına kapsam sağlayacak ve topluluğun yükseltmeleri önermesine ve araştırmasına olanak tanıyacaktır.

2. **Sistem Akıllı Sözleşmeleri Yönetişimi**: Bu temel, akıllı sözleşmeler olarak uygulanan protokol bileşenlerinin yükseltilebilirliğine odaklanır. Topluluk tarafından yönetilen bir Ekosistem Konseyi, bu yükseltmelerden sorumlu olacaktır. Konsey, güvenli ve ölçeklenebilir karar verme için özel olarak tasarlanmış bir yönetişim çerçevesi altında çalışacaktır.

3. **Topluluk Hazinesi Yönetişimi**: Kendini sürdürebilir bir Topluluk Hazinesi, kamu yararına olan projeleri finanse etmek ve umut verici ekosistem projelerini desteklemek için kurulacaktır. Bu hazine'nin yönetişimi, başlangıçtaki bir kuruldan daha açık topluluk tarafından yönlendirilen yönetişim mekanizmalarına evrilecektir.

<p align="center">
<img align="center" src="/static/img/readme/polygon2.0-governance-pillars.png" width="900">
</p>

#### Topluluk Katılımı

Topluluk geri bildirimleri ve katılımı, yönetişim sürecinin ayrılmaz bir parçasıdır. Doğrulayıcılar, kullanıcılar, altyapı sağlayıcılar ve dApp geliştiricilerinden geri bildirim almak için çeşitli kanallar, forum gönderileri ve topluluk çağrıları dahil, kullanılır.

### Tokenomik

Polygon'un yerel tokeni MATIC, 2020'deki kuruluşundan bu yana ağın büyümesinde kilit bir rol oynamıştır. Polygon 2.0'ın tanıtılmasıyla, MATIC'e teknik bir yükseltme olarak yeni bir token, **POL**, önerilmektedir. POL, sahiplerine çeşitli faydalar ve teşvikler sunacak şekilde tasarlanmış üçüncü nesil hiper üretken bir token olarak tasarlanmıştır.

#### POL'un Ana Özellikleri

- **Üçüncü Nesil Token**: POL, hiper üretken token kavramını tanıtır. İlk ve ikinci nesil tokenlerin aksine, POL sahiplerinin birden fazla zinciri doğrulamasına ve bu zincirler içinde birden fazla rol üstlenmesine olanak tanır, bu sayede pratiğe dökülebilir sınırsız fırsatlar sunar.

- **Büyük Faydalar**: POL, kullanıcılar ve geliştiriciler için sürtünme yaratmadan ekosistem güvenliği, sonsuz ölçeklenebilirlik ve topluluk sahipliği sağlamayı amaçlar.

- **Çok Yönlü Fayda ve Teşvikler**: Doğrulayıcılar, doğrulayıcı kümesine katılmak için POL yatırmak zorundadır. Bir kez yatırıldığında, herhangi bir Polygon zincirini doğrulayabilir ve protokol ödülleri, işlem ücretleri ve ekstra ödüller dahil olmak üzere birden fazla teşvik akışı oluşturabilirler.

- **Geleceğe Dayanıklı Ekosistem**: POL, bir Topluluk Hazinesini finanse etmek için sürekli bir emisyona sahip olacaktır, bu hazine Polygon topluluğu tarafından yönetilecektir. Bu hazine, protokol gelişimini, araştırmayı, ekosistem burslarını ve benimsenme teşviklerini destekleyecektir.

- **Problemsiz Yükseltme**: MATIC'ten POL'a geçiş, basit bir teknik işlemle kolaylaştırılacaktır. Token sahipleri MATIC'i bir yükseltme akıllı sözleşmesine gönderecek ve bu otomatik olarak eşdeğer miktarda POL döndürecektir.

### Polygon'un Geliştirme Çerçevelerinin Evrimi

Polygon'un egemen blok zincirleri inşa etmek için blok zinciri geliştirme çerçevesi zamanla önemli ölçüde evrim geçirmiştir, her iterasyon yeni özellikler ve yetenekler getirmiştir. Aşağıda, Polygon Edge, Supernets ve en son Zincir Geliştirme Kiti (CDK) arasındaki ana farkları ve özellikleri özetleyen bir karşılaştırma tablosu bulunmaktadır.

#### Çerçeve Karşılaştırması

| Özellik              |  Edge       | Supernets  | CDK                           |
|---------------------|-------------|------------|-------------------------------|
| **Katman**          | Katman 3    | Katman 3   | Katman 2                       |
| **Konsensus**       | IBFT        | PolyBFT    | zk-tabanlı / PolyBFT          |
| **Odak**            | Uygulama Zincirleri| Uygulama Zincirleri, Altyapı ve Özelleştirmeler | Uygulama Zincirleri, Altyapı, Özelleştirmeler, Modüler Geliştirme, Maliyet Azaltma |
| **Ölçeklenebilirlik**| Sınırlı    | Genişletilmiş Blok Alanı | Sınırsız                    |
| **Entegrasyon**     | Sınırlı     | Özel Yerel Köprü          | Evrensel Katmanlı Köprü     |
| **Yönetişim**       | Yok        | Özelleştirilebilir | Özelleştirilebilir           |
| **Veri Erişilebilirliği**| Zincir İçi| Zincir İçi | Özelleştirilebilir            |
| **Modülerlik**      | Sınırlı     | Sınırlı    | Evet                           |
| **Bileşenler**      | Edge istemcisi + Ethereum'da çekirdek sözleşmeler | Edge istemcisi + EVM-tabanlı kök zincir + egemen çekirdek sözleşmeler | Polygon 2.0'ın bir parçası olan özelleştirilebilir bileşenler |

#### Ana Çıkarımlar

- **Polygon Edge**: İlk olarak, Ethereum uyumlu blok zinciri ağları oluşturmak için uygulama zincirleri başlatmak amacıyla bir SDK olarak hizmet verdi, Katman 3 çözümleri olarak işlev gördü.

- **Polygon Supernets**: Edge'den evrim geçirerek uygulama zincirleri için altyapı geliştirme ve önyükleme karmaşıklıklarıyla başa çıkmayı amaçlar. Supernets, ayrıca gelişmiş entegrasyon ve özelleştirme seçenekleri sunar, aynı zamanda Katman 3 çözümleri olarak işlev görür.

- **Polygon CDK**: En yeni ve sofistike iterasyon olan CDK, Katman 2 çözümlerine odaklanır. Modülerliği ve özelleştirilebilirliği somutlaştırır, Polygon 2.0'dan keskin protokol ilkelini kullanır. Bu, geliştiricilerin benzersiz gereksinimlere uygun zincirler mimarlamalarını sağlar.

<p align="center">
<img align="center" src="/static/img/readme/polygon2.0-layers-1.png" width="900">
</p>

https://github.com/0xPolygon/wiki/assets/25497083/d848aecf-7f20-41d1-8382-80a41c622b25

## Ana Polygon Depoları

Polygon ekosistemini güçlendiren temel kod tabanlarını keşfedin. Bu bölüm, geliştiriciler, şirketler ve topluluk üyeleri için bir başlangıç noktası olarak en temel depolar için hızlı bağlantılar ve açıklamalar sunar.

### 0xPolygon Altında Polygon 2.0 Depoları

| Kategori                 | Depo Adı                                                         | Açıklama                                                                                       |
|--------------------------|------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| **Edge**                 | [Polygon Edge](https://github.com/0xPolygon/polygon-edge)         | Polygon'un kenar hizmetleri için bir depo.                                                     |
| **CDK**                  | [CDK Validium Node](https://github.com/0xPolygon/cdk-validium-node)| Validium düğümü dağıtımı için bir CDK.                                                         |
|                          | [CDK Veri Erişilebilirliği](https://github.com/0xPolygon/cdk-data-availability)| Veri erişilebilirlik çözümleri için bir CDK.                                                   |
|                          | [CDK Validium Sözleşmeler](https://github.com/0xPolygon/cdk-validium-contracts)| CDK Validium tarafından kullanılacak olan akıllı sözleşme uygulaması.                           |
| **Çekirdek**             | [Çekirdek Sözleşmeler](https://github.com/0xPolygon/core-contracts)| Polygon ağının çekirdeğini oluşturan akıllı sözleşmeler.                                       |
| **DApps ve Keşif**       | [DApp Keşif Polygon](https://github.com/0xPolygon/dapp-explorer-polygon)| Polygon ağı için bir DApp keşif platformu.                                                      |
| **Köprüler ve Entegrasyon** | [PoS ZkEVM Köprü](https://github.com/0xPolygon/pos-zkevm-bridge)| PoS ortamında ZkEVM için bir köprü.                                                             |
| **Araçlar**              | [Gaz Değiştirici](https://github.com/0xPolygon/gas-swapper)        | Gaz değişimi için bir araç.                                                                     |
|                          | [Indicia](https://github.com/0xPolygon/indicia)                   | Indicia, bir Polygon servisi için bir depo.                                                     |
| **ZkEVM**                | [ZkEVM Sarıcı](https://github.com/0xPolygon/zkevm-wrapper)         | ETH ve ERC20 tokenlerini ZkEVM'e transfer etmek için sarıcı sözleşmeler.                        |
| **Ekonomik Modeller**    | [Polygon 2.0 Ekonomik Model](https://github.com/0xPolygon/polygon2.0-economic-model)| Polygon 2.0'da doğrulayıcı teşvikleri ve ekosistem güvenliğini incelemek için bir simülasyon modeli.  |

### 0xPolygonHermez Altında zkEVM Depoları

| Kategori                  | Depo Adı                                                            | Açıklama                                                                                       |
|---------------------------|---------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| **Kanıtlayıcı (Prover)**  | [zkEVM Kanıtlayıcı](https://github.com/0xPolygonHermez/zkevm-prover)  | ZkEVM için kanıtlayıcı.                                                                         |
| **Düğüm (Node)**          | [zkEVM Düğüm](https://github.com/0xPolygonHermez/zkevm-node)         | ZkEVM için düğüm uygulaması.                                                                    |
| **Sözleşmeler**           | [zkEVM Sözleşmeler](https://github.com/0xPolygonHermez/zkevm-contracts)| ZkEVM için akıllı sözleşmeler.                                                                  |
| **Köprü Hizmeti**         | [zkEVM Köprü Hizmeti](https://github.com/0xPolygonHermez/zkevm-bridge-service)| ZkEVM için köprü hizmeti.                                                                       |
| **PIL Kütüphaneleri**     | [PIL2 Stark JS](https://github.com/0xPolygonHermez/pil2-stark-js)    | PIL2 STARK'lar için JavaScript kütüphanesi.                                                     |
|                           | [PILCOM](https://github.com/0xPolygonHermez/pilcom)                  | ZkEVM için PILCOM kütüphanesi.                                                                  |
| **Test Vektörleri**       | [zkEVM Test Vektörleri](https://github.com/0xPolygonHermez/zkevm-testvectors)| ZkEVM için test vektörleri.                                                                     |
| **Ortak Kütüphaneler**    | [zkEVM CommonJS](https://github.com/0xPolygonHermez/zkevm-commonjs)  | ZkEVM için CommonJS kütüphanesi.                                                                |
| **İletişim Protokolleri** | [zkEVM İletişim Protokolü](https://github.com/0xPolygonHermez/zkevm-comms-protocol)| ZkEVM için iletişim protokolü.                                                                  |
| **JavaScript Kanıtlayıcılar** | [zkEVM ProverJS](https://github.com/0xPolygonHermez/zkevm-proverjs) | ZkEVM için JavaScript kanıtlayıcı.                                                              |
| **Goldilocks**            | [Goldilocks](https://github.com/0xPolygonHermez/goldilocks)          | ZkEVM için Goldilocks kütüphanesi.                                                              |
| **PIL STARK**             | [PIL STARK](https://github.com/0xPolygonHermez/pil-stark)            | ZkEVM için PIL STARK kütüphanesi.                                                               |
| **ROM**                   | [zkEVM ROM](https://github.com/0xPolygonHermez/zkevm-rom)            | ZkEVM için Salt Okunur Bellek (Read-Only Memory).                                               |
| **ASM Derleyici**         | [zkASMCOM](https://github.com/0xPolygonHermez/zkasmcom)              | ZkEVM için ZkASM derleyici.                                                                     |
### MaticNetwork Altında Polygon PoS Depoları

| Kategori                  | Depo Adı                                                            | Açıklama                                                                                       |
|---------------------------|---------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| **Çekirdek Bileşenler**   | [Heimdall](https://github.com/maticnetwork/heimdall)                 | PoS Ağı için Heimdall katmanı.                                                                 |
|                           | [Bor](https://github.com/maticnetwork/bor)                           | PoS Ağı için Bor düğümü.                                                                       |
|                           | [Tendermint](https://github.com/maticnetwork/tendermint)             | PoS uyumlu konsensus motoru için Tendermint çatalı.                                             |
|                           | [Cosmos SDK](https://github.com/maticnetwork/cosmos-sdk)             | PoS Ağı için Cosmos SDK çatalı.                                                                 |
| **Token Yönetimi**        | [Polygon Token Listesi](https://github.com/maticnetwork/polygon-token-list)| PoS ağındaki tokenlerin listesi.                                                              |
|                           | [Polygon Token Varlıkları](https://github.com/maticnetwork/polygon-token-assets)| PoS ağı için token varlıkları.                                                                |
| **Altgraflar**           | [Altgraflar](https://github.com/maticnetwork/subgraphs)              | PoS Ağı için altgraflar.                                                                       |
| **CLI Araçları**          | [Matic CLI](https://github.com/maticnetwork/matic-cli)               | PoS Ağı için komut satırı arayüzü.                                                             |
|                           | [Polygon CLI](https://github.com/maticnetwork/polygon-cli)           | Polygon için komut satırı arayüzü.                                                             |
| **Gaz Yönetimi**          | [Matic Gaz İstasyonu](https://github.com/maticnetwork/maticgasstation)| PoS Ağı için gaz istasyonu.                                                                    |
| **Portallar ve Köprüler** | [PoS Portal](https://github.com/maticnetwork/pos-portal)             | PoS Ağı için Kanıt Temelli Sahiplik (Proof of Stake) portalı.                                  |
| **Teklifler**             | [Polygon İyileştirme Teklifleri](https://github.com/maticnetwork/Polygon-Improvement-Proposals)| Polygon İyileştirme Teklifleri için depo.                                                       |
| **SDK'lar ve Kütüphaneler**| [Matic.js](https://github.com/maticnetwork/matic.js)                 | PoS Ağı için JavaScript kütüphanesi.                                                            |
| **DevOps**                | [Düğüm Ansible](https://github.com/maticnetwork/node-ansible)         | Düğüm yönetimi için Ansible scriptleri.                                                         |
|                           | [Terraform Polygon Supernets](https://github.com/maticnetwork/terraform-polygon-supernets)| Polygon Supernets için Terraform scriptleri.                                                    |
| **Sözleşmeler**           | [Sözleşmeler](https://github.com/maticnetwork/contracts)             | PoS Ağı için akıllı sözleşmeler.                                                                |
|                           | [Başlangıç Sözleşmeleri](https://github.com/maticnetwork/genesis-contracts)| PoS Ağı için başlangıç sözleşmeleri.                                                            |
| **Kanıtlar ve API'ler**   | [Kanıt Oluşturma API](https://github.com/maticnetwork/proof-generation-api)| Kanıt oluşturma için API.                                                                       |
| **Erigon**                | [Erigon](https://github.com/maticnetwork/erigon)                     | Erigon Ethereum istemcisi.                                                                      |
| **Politikalar**           | [Polygon'da Politika](https://github.com/maticnetwork/Policy-at-Polygon)| Polygon'da politikalar.                                                                         |

---

# Repository Overview

This section delves into the specifics of this repository, explaining its structure, the types of files and folders it contains, and how to navigate it. It serves as a guide for developers and contributors who are interested in the source code, documentation, or contributing to the project.

## State of the Docs

In sync with the ongoing advancements of Polygon 2.0, the Polygon documentation platform is also slated for significant enhancements. Originally conceived as a "Developer Hub," the platform evolved into a "Wiki" in an attempt to effectively meet the distinct needs of various projects. 

While termed a "Wiki," the platform transcends the traditional scope of a wiki, serving as more than just a repository of information. This is because it aims serve as a versatile platform that accommodates different types of technical content and the diverse needs and stages of project development.

### What to Expect?

- **Unified Experience**: Seamlessly integrated with the main Polygon website, the documentation will feature a new, dynamic learning experience. The source will maintain its independent existence for continued integrity and versatility.
- **Dynamic Documentation**: Transition from a static information repository to an interactive, dynamic knowledge platform.
- **Enhanced Learning Experience**: Intuitive and enriching content tailored to facilitate learning, whether you're a beginner or an expert.
- **User-Centric Design**: Improved information architecture and navigation, designed with different user personas in mind, all guided by principles of developer advocacy and product development.

The Polygon community is committed to offering a comprehensive and current resource that helps users stay at the cutting edge of blockchain technology. Watch this space for more updates.

## Configuration Guide

### Static-Site Generator

The [Polygon Wiki](https://wiki.polygon.technology/) is built using [Docusaurus](https://docusaurus.io/), making it easy to serve and host its static files.

### Deployments

The deployment process for the Polygon Wiki involves two environments: **staging** and **prod**. Both environments are configured to run against the `main` branch of the repository.

Any deployment—whether to Staging or Production—requires explicit authorization from an admin of the repository.

- **Staging**: This environment is used for testing and quality assurance. Changes are deployed here first to ensure they meet the required standards before moving to Production.
- **Production**: This is the live environment accessible to the end-users. Deployments to Production are made after successful validation in the Staging environment.

### Algolia DocSearch

The documentation utilizes [Algolia's DocSearch](https://docsearch.algolia.com/) to provide a powerful and user-friendly search experience. DocSearch is specifically designed to improve navigation in documentation websites, making it easier for users to find the information they need.

### Google Analytics

[Google Analytics](https://analytics.google.com/) is integrated into the platform to monitor user interactions and collect valuable data. This helps in understanding user engagement and behavior, thereby aiding in the continuous improvement of the documentation. For those curious about how data is handled, please refer to our [Terms of Use](https://polygon.technology/terms-of-use).

### Translations

| ❗ The Wiki is undergoing a reorganization and update. Translation efforts will resume upon completion of this revamp.       |
| ---------------------------------------------------------------------------------------------------------------------------- |

### Files and Folders

This section provides an overview of the various files and folders in the Polygon Wiki repository, explaining the purpose of each.

| Name                  | Purpose                                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------------------|
| `.git`, `.github`     | Manage git configurations and GitHub-specific settings.                                                          |
| `README.md`           | The main introduction file for the Polygon Wiki repository.                                                      |
| `sidebars.js`         | Used to modify the sidebar navigation.                                                                           |
| `docusaurus.config.js`| Configuration file for website layout and other Docusaurus settings.                                             |
| `src/pages/index.js`  | Used to modify the blocks structure and footer links.                                                            |
| `yarn.lock`           | Yarn lock file to keep track of all package versions.                                                           |
| `package.json`        | Specifies dependencies and scripts for the project.                                                              |
| `node_modules/`       | Contains all the npm packages and dependencies.                                                                  |
| `build/`              | Contains static content generated for deployment.                                                                |
| `docs/`               | Contains the Markdown files that make up the content of the Wiki.                                                |
| `static/`             | Contains static assets like images, CSS, and fonts.                                                              |
| `translations/`       | Contains files for managing different languages.                                                                 |

> Note: This is a general overview and the actual repository may contain additional files and folders for specific functionalities.

### Priority Labels (`P#`)

GitHub labels are used to categorize the urgency and importance of issues. These priority levels are set by the documentation team based on the following criteria:

| Label | Impact Level                 | Resolution Time | Example Use Case                                                  |
|-------|-----------------------------|--------------------------|-------------------------------------------------------------------|
| P0    | Critical ("Urgent"): Requires immediate attention | Same day: Drop all other tasks and resolve immediately | The website is down, causing a severe impact on the business.      |
| P1    | High ("Important"): Significant business impact | Within 3 days: Must be addressed promptly | An API endpoint is changing, requiring immediate documentation updates. |
| P2    | Medium ("Sometime Soon"): Scheduled or planned | Within 2-3 weeks: Can be scheduled for near-term completion | Upcoming addition of a new method to a project API.                |
| P3    | Low ("Nice to Have"): Suggestions or conceptual updates | No set deadline: Address when possible | A suggested blog post on the advantages of decentralization for developers. |

## How to Contribute to the Polygon Wiki

The Documentation team at Polygon Labs are the primary maintainers of the Polygon Wiki and will
review all issues and pull requests created in this repository. If you spot typos or grammar mistakes, 
please go ahead and submit a pull request with the fixes. For bigger changes, it's a good idea to start with a GitHub 
issue to discuss it with the maintainers. We generally prefer pull requests over issues for suggesting changes to the Wiki.

| ❗ We've set up guidelines to make sure all new contributions keep improving the Wiki without compromising its quality. They are available [here](https://wiki.polygon.technology/docs/contribute/orientation/). |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Before making a contribution, please consult any existing issues or initiate a new discussion to ensure alignment with the Wiki's objectives.
Once you've done that, you'll find that your contributions can significantly enrich the Wiki in the following ways:

1. **General Overviews**: Introductory pieces that offer a holistic understanding of Polygon's ecosystem, including its core infrastructure and Layer 2 solutions.

2. **Technical Deep Dives**: In-depth articles that explore specific components of Polygon's architecture, such as its protocol layers, primitives, and consensus algorithms.

3. **Use-Case Scenarios**: Articles that showcase real-world applications of Polygon in various sectors like DeFi, NFTs, supply chain, and more.

4. **Interoperability Explainers**: Contributions that clarify how Polygon interfaces with other blockchain ecosystems, Layer 1 solutions, or cross-chain platforms.

5. **Tooling**: Documentation or guides on tools that facilitate development, testing, or deployment on Polygon. This could include IDE plugins, testing frameworks, or monitoring tools.

6. **Third-Party Services**: Information on external services that integrate with Polygon, such as oracles, data analytics platforms, or liquidity providers.

7. **Community Contributions**: Lists of active Polygon communities, educational resources, or upcoming events that enrich the ecosystem.

8. **Governance & Economics**: Insights into the governance model and tokenomics that underpin Polygon's network.

9. **Security Practices**: Guidelines and resources for ensuring the security and integrity of dApps, smart contracts, and general infrastructure on Polygon.

10. **Troubleshooting Guides**: Solutions to common challenges, FAQs, and other resources that assist both newcomers and experienced users.

11. **Emerging Technologies**: Articles on upcoming features, Layer 2 advancements, or experimental technologies that are in the Polygon pipeline.

| ❗ Note: The Polygon Wiki includes third-party content. Please review the [Third-Party Content Disclaimer](https://github.com/0xPolygon/wiki/blob/main/CONTENT_DISCLAIMER.md) for details. |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- |

### How to Contribute Changes via the Polygon Wiki Website

Contributing to the Polygon Wiki is straightforward. You'll need a GitHub account and a basic understanding of Markdown syntax to get started.

1. **Locate the Page**: Visit the [Polygon Wiki page](https://wiki.polygon.technology/) you wish to edit.
2. **Navigate to the Bottom**: Scroll to the bottom of the page.
3. **Edit Link**: Click on the **Edit this page** link. This will redirect you to the corresponding Markdown file on GitHub.
4. **Edit Mode**: Once on GitHub, click the pencil icon located in the upper-right corner to enter edit mode.
5. **Make Edits**: Modify the Markdown file as needed.
6. **Initiate Pull Request**: Scroll to the bottom and click on **Create pull request**.
7. **Title Your PR**: Give your pull request a descriptive title. For instance, if you're editing the "Getting Started" page, you could title it *Update /docs/develop/getting-started.md*.
8. **Describe Changes**: In the pull request description, specify the issue your changes resolve. 
   > See [GitHub Docs on Linking a Pull Request to an Issue](https://docs.github.com/en/free-pro-team@latest/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword) for guidance.
9. **Additional Information**: Provide a concise summary of the changes you've made. Include screenshots or references if applicable.
10. **Submit**: Click **Propose changes** to finalize your pull request. This will create a new branch in your fork.

A Polygon Wiki maintainer will review your pull request. If approved, it will be merged into the `main` branch.

### How to Locally Run the Polygon Wiki

> **Prerequisites**:  
> - [Node.js](https://nodejs.org/en/download/) (version >= 16.14.1)  
> - [Yarn](https://yarnpkg.com/getting-started/install) (version >= 1.22)  
> **Note for macOS Users**: Xcode and Command Line Tools are required.

#### Setup Steps

1. **Fork the Repository**  
   > See [GitHub Docs: Fork a repo](https://help.github.com/en/articles/fork-a-repo) for guidance.

2. **Clone Your Fork**

   ```bash
   git clone git@github.com:[your_github_handle]/wiki.git
   ```

3. **Navigate to the Repository**

    ```bash
    cd wiki
    ```

4. **Add Upstream Remote**
   > Refer to [GitHub Docs: Configuring a remote for a fork](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/configuring-a-remote-for-a-fork).
   
    ```bash
    git remote add upstream https://github.com/0xPolygon/wiki
    ```

5. **Sync Your Fork**
   > See [GitHub Docs: Syncing a fork](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/syncing-a-fork).

    ```bash
    git checkout master
    git fetch upstream
    git merge upstream/master
    ```

6. **Install Dependencies**
   
    ```bash
    yarn install
    ```
    
   The site is built using Docusaurus. You may need to install Docusaurus before running the Wiki locally.

   ```bash
   yarn add docusaurus
   ```
   
   Alternatively, you can upgrade Docusaurus.

   ```bash
   yarn upgrade @docusaurus/core@latest @docusaurus/preset-classic@latest
   ```

7. **Run the Wiki Locally**

    ```bash
    yarn start
    ```

## Primary Maintainers

Below is a list of the primary maintainers of the Polygon Wiki.

If you're ever contacted by one of these individuals, take the following steps to ensure the communication is legitimate:

1. **Verify Contact Information**: Match the contact details with the origin of the message.
2. **Double-Check**: Reach out to another person on this list to confirm the legitimacy of the initial contact.

| ❗ Beware of Impersonation Scams: Always cross-verify the identity of the person contacting you. Confirm that their contact details align with the message source and seek additional verification when in doubt.|
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- |

- [@DannyS03](https://github.com/DannyS03): Lead contact, primarily focuses on CDK, PoS & ZK, along with project organization.
- [@EmpieichO](https://github.com/EmpieichO): Primarily focusses on zkEVM & Miden, and specifications.
- [@cerberushades](https://github.com/cerberushades): Primarily focuses on Polygon ID.

## License

The Polygon Wiki is licensed under the [MIT License](LICENSE) free software license.
