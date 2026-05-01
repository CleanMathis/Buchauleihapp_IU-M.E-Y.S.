# Buchauleihapp_IU-M.E-Y.S.
Die Datenbank für eine Buchausleihapp.
-- --------------------------------------------------------
-- Host:                         127.0.0.1
-- Server-Version:               12.1.2-MariaDB - MariaDB Server
-- Server-Betriebssystem:        Win64
-- HeidiSQL Version:             12.11.0.7065
-- --------------------------------------------------------

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET NAMES utf8 */;
/*!50503 SET NAMES utf8mb4 */;
/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */;
/*!40103 SET TIME_ZONE='+00:00' */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;


-- Exportiere Datenbank-Struktur für BuchAusleihApp
CREATE DATABASE IF NOT EXISTS `buchausleihapp` /*!40100 DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_uca1400_ai_ci */;
USE `BuchAusleihApp`;

-- Exportiere Struktur von Tabelle BuchAusleihApp.admin
CREATE TABLE IF NOT EXISTS `admin` (
  `admin_id` int(11) NOT NULL AUTO_INCREMENT COMMENT 'Id, zur Identifikation',
  `username` varchar(50) NOT NULL COMMENT 'Das was man im UI sieht + Login',
  `vorname` varchar(50) NOT NULL COMMENT 'Für Betreiber der App, sowas wie Mitarbeiter',
  `nachname` varchar(50) NOT NULL,
  `email` varchar(50) NOT NULL COMMENT 'Kontaktierungsmöglichkeit',
  `password_hash` varchar(50) NOT NULL COMMENT 'Login',
  PRIMARY KEY (`admin_id`)
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_uca1400_ai_ci;

-- Exportiere Daten aus Tabelle BuchAusleihApp.admin: ~10 rows (ungefähr)
INSERT IGNORE INTO `admin` (`admin_id`, `username`, `vorname`, `nachname`, `email`, `password_hash`) VALUES
	(1, 'admino', 'Adri', 'Parks', 'parks_ardo@gmail.com', 'KSDAÖß9876LG'),
	(2, 'saosa', 'Oswalt', 'Gregors', 'o.gregors@testmail.de', 'LÖKJSHDF09ß435'),
	(3, 'xbDq', 'Ichael', 'Erz', 'ichael.erz@web.de', 'LJKSDAGHF4ß52376ß'),
	(4, 'Helfer', 'Wasley', 'Lighters', 'w.lighters@service.com', 'LKJHDSFAGß0435276'),
	(5, 'trues', 'Marker', 'Krugs', 'marker.krugs@provider.net', 'PWQEORZUß4305276'),
	(6, 'eiene', 'Lankes', 'Lankes', 'lankes.lankes@mail.org', 'M:;NXYCBVß2310754'),
	(7, 'echter', 'Papil', 'Ione', 'papil.ione@gmail.com', '4r435zhgfdh'),
	(8, '123streit', 'Lionel', 'Messi', 'l.messi@goat.com', '4765856FHGEDIUZT'),
	(9, 'ist', 'Rivalo', 'Cris', 'rivalo.cris@soccer.br', '698070dfghjfSFD'),
	(10, 'vorbeiei', 'Cristiano', 'Ronaldo', 'cr7.official@football.com', 'RSTZR43675');

-- Exportiere Struktur von Tabelle BuchAusleihApp.adresse
CREATE TABLE IF NOT EXISTS `adresse` (
  `adress_id` int(11) NOT NULL AUTO_INCREMENT COMMENT 'Referenz wichtig, wo wer wohnt und fürs Ausleihen',
  `land` varchar(50) NOT NULL DEFAULT '' COMMENT 'Adressdaten',
  `postleihzahl` int(5) NOT NULL COMMENT 'Adressdaten',
  `stadt` varchar(50) NOT NULL COMMENT 'Adressdaten',
  `strasse` varchar(50) NOT NULL COMMENT 'Adressdaten',
  `hausnummer` int(11) NOT NULL COMMENT 'Adressdaten',
  `geodaten` point NOT NULL COMMENT 'Berechnung in der Nähe, wenn Radius in der Suche',
  PRIMARY KEY (`adress_id`)
) ENGINE=InnoDB AUTO_INCREMENT=21 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_uca1400_ai_ci;

-- Exportiere Daten aus Tabelle BuchAusleihApp.adresse: ~10 rows (ungefähr)
INSERT IGNORE INTO `adresse` (`adress_id`, `land`, `postleihzahl`, `stadt`, `strasse`, `hausnummer`, `geodaten`) VALUES
	(1, 'Deutschland', 60313, 'Frankfurt am Main', 'Zeil', 106, _binary 0xe61000000101000000053411363c5d21402db29defa70e4940),
	(2, 'Deutschland', 65719, 'Hofheim am Taunus', 'Zeil', 33, _binary 0xe61000000101000000053411363c5d21402db29defa70e4940),
	(3, 'Deutschland', 62830, 'Kriftel', 'Gartenstr.', 64, _binary 0xe61000000101000000053411363c5d21402db29defa70e4940),
	(4, 'Deutschland', 64560, 'Riedstadt', 'Brillenstr.', 321, _binary 0xe61000000101000000053411363c5d21402db29defa70e4940),
	(5, 'Deutschland', 60313, 'Frankfurt am Main', 'Sonnenalle', 231, _binary 0xe61000000101000000053411363c5d21402db29defa70e4940),
	(6, 'Deutschland', 12354, 'Berlin', 'Kotti', 32, _binary 0xe61000000101000000053411363c5d21402db29defa70e4940),
	(7, 'Deutschland', 14354, 'Kaltbach', 'Meilastr.', 22, _binary 0xe61000000101000000053411363c5d21402db29defa70e4940),
	(8, 'Deutschland', 60069, 'Imaginärstadt', 'Traumstr.', 76, _binary 0xe61000000101000000053411363c5d21402db29defa70e4940),
	(9, 'Deutschland', 65734, 'Eschborn', 'Misstrau', 45, _binary 0xe61000000101000000053411363c5d21402db29defa70e4940),
	(10, 'Deutschland', 60313, 'Frankfurt am Main', 'Valita', 6069, _binary 0xe61000000101000000053411363c5d21402db29defa70e4940);

-- Exportiere Struktur von Tabelle BuchAusleihApp.bewertung
CREATE TABLE IF NOT EXISTS `bewertung` (
  `bew_id` int(11) NOT NULL AUTO_INCREMENT COMMENT 'Identifikation',
  `überschrift` varchar(50) NOT NULL COMMENT 'Überschrift vom Kommentar',
  `sterne` int(1) DEFAULT NULL COMMENT 'Bewertungsmethode',
  `kommentar` text NOT NULL COMMENT 'Die Bewertung',
  `leih_id` int(11) NOT NULL COMMENT 'Referenz, auf andere Daten, wie Besitzer, Buch und Ausleiher',
  PRIMARY KEY (`bew_id`),
  KEY `leihe` (`leih_id`),
  CONSTRAINT `leihe` FOREIGN KEY (`leih_id`) REFERENCES `leihe_rückgabe` (`leih_id`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_uca1400_ai_ci;

-- Exportiere Daten aus Tabelle BuchAusleihApp.bewertung: ~10 rows (ungefähr)
INSERT IGNORE INTO `bewertung` (`bew_id`, `überschrift`, `sterne`, `kommentar`, `leih_id`) VALUES
	(1, 'Der Schwarm', 5, 'Packender Öko-Thriller, extrem spannend recherchiert.', 1),
	(2, 'Die unendliche Geschichte', 5, 'Ein zeitloser Klassiker der Fantasyliteratur.', 2),
	(3, 'QualityLand', 4, 'Erschreckend komische Vision unserer digitalen Zukunft.', 3),
	(4, 'Der Vorleser', 4, 'Ein tiefgründiges Werk über Schuld und Generationen.', 4),
	(5, 'Siddhartha', 5, 'Wunderschöne Erzählung über die Suche nach Erkenntnis.', 5),
	(6, 'Die Physiker', 3, 'Interessantes Drama über die Verantwortung der Wissenschaft.', 6),
	(7, 'NSA - Nationales Sicherheits-Amt', 4, 'Beklemmendes Gedankenspiel über Überwachung im Dritten Reich.', 7),
	(8, 'Faust Teil 1', 5, 'Das bedeutendste Werk der deutschen Literatur.', 8),
	(9, 'Tyll', 4, 'Großartiger historischer Roman über den Dreißigjährigen Krieg.', 9),
	(10, 'Im Westen nichts Neues', 5, 'Erschütterndes und wichtiges Anti-Kriegs-Epos.', 10);

-- Exportiere Struktur von Tabelle BuchAusleihApp.buch_exemplar
CREATE TABLE IF NOT EXISTS `buch_exemplar` (
  `exemp_id` int(11) NOT NULL AUTO_INCREMENT COMMENT 'exemplar_id, wenn mehrer Besitzer selbes Buch, hier weniger Speicher',
  `titel` varchar(50) NOT NULL DEFAULT '' COMMENT 'Metadaten',
  `autor` varchar(50) NOT NULL DEFAULT '' COMMENT 'Metadaten',
  `genre` varchar(50) NOT NULL COMMENT 'Metadaten',
  `veroeff_jahr` int(11) NOT NULL DEFAULT 0 COMMENT 'Metadaten',
  `sprache` varchar(50) NOT NULL COMMENT 'Metadaten',
  PRIMARY KEY (`exemp_id`)
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_uca1400_ai_ci COMMENT='Trennung von Buchexemplar und dem physichen';

-- Exportiere Daten aus Tabelle BuchAusleihApp.buch_exemplar: ~10 rows (ungefähr)
INSERT IGNORE INTO `buch_exemplar` (`exemp_id`, `titel`, `autor`, `genre`, `veroeff_jahr`, `sprache`) VALUES
	(1, 'Der Schwarm', 'Frank Schätzing', 'Science Fiction', 2004, 'deutsch'),
	(2, 'Die unendliche Geschichte', 'Michael Ende', 'Fantasy', 1979, 'deutsch'),
	(3, 'QualityLand', 'Marc-Uwe Kling', 'Satire', 2017, 'deutsch'),
	(4, 'Der Vorleser', 'Bernhard Schlink', 'Roman', 1995, 'deutsch'),
	(5, 'Siddhartha', 'Hermann Hesse', 'Erzählung', 1922, 'deutsch'),
	(6, 'Die Physiker', 'Friedrich Dürrenmatt', 'Drama', 1962, 'deutsch'),
	(7, 'NSA - Nationales Sicherheits-Amt', 'Andreas Eschbach', 'Thriller', 2018, 'deutsch'),
	(8, 'Faust: Der Tragödie erster Teil', 'Johann Wolfgang von Goethe', 'Tragödie', 1808, 'deutsch'),
	(9, 'Tyll', 'Daniel Kehlmann', 'Historischer Roman', 2017, 'deutsch'),
	(10, 'Im Westen nichts Neues', 'Erich Maria Remarque', 'Kriegsroman', 1929, 'deutsch');

-- Exportiere Struktur von Tabelle BuchAusleihApp.buch_physisch
CREATE TABLE IF NOT EXISTS `buch_physisch` (
  `buch_id` int(11) NOT NULL AUTO_INCREMENT COMMENT 'Identifikatin',
  `zustand` varchar(50) NOT NULL COMMENT 'Bei Schadnsfällen',
  `verfuegbar` bit(1) NOT NULL COMMENT 'Um doppeltes Ausleihen verhindern, wenn Buch geliehen ist',
  `besitzer_id` int(11) NOT NULL COMMENT 'Wem gehört es, wo er wohnt ',
  `exemp_id` int(11) NOT NULL COMMENT 'Referenz auch Exemplar, kann Speicher schonen',
  PRIMARY KEY (`buch_id`),
  KEY `besitzer` (`besitzer_id`) USING BTREE,
  KEY `Exemplar_id` (`exemp_id`),
  CONSTRAINT `Exemplar_id` FOREIGN KEY (`exemp_id`) REFERENCES `buch_exemplar` (`exemp_id`) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT `besitzer` FOREIGN KEY (`besitzer_id`) REFERENCES `nutzer` (`user_id`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_uca1400_ai_ci COMMENT='Das Buch des Besitzers';

-- Exportiere Daten aus Tabelle BuchAusleihApp.buch_physisch: ~10 rows (ungefähr)
INSERT IGNORE INTO `buch_physisch` (`buch_id`, `zustand`, `verfuegbar`, `besitzer_id`, `exemp_id`) VALUES
	(1, 'sehr gut', b'1', 1, 1),
	(2, 'gut', b'0', 2, 2),
	(3, 'sehr gut', b'1', 3, 3),
	(4, 'mittel', b'0', 4, 4),
	(5, 'gut', b'1', 1, 5),
	(6, 'mittel', b'0', 2, 6),
	(7, 'sehr gut', b'0', 3, 7),
	(8, 'mittel', b'1', 4, 8),
	(9, 'sehr gut', b'1', 1, 9),
	(10, 'gut', b'0', 2, 10);

-- Exportiere Struktur von Tabelle BuchAusleihApp.leihe_rückgabe
CREATE TABLE IF NOT EXISTS `leihe_rückgabe` (
  `leih_id` int(11) NOT NULL AUTO_INCREMENT COMMENT 'Identifikation',
  `buch_id` int(11) NOT NULL COMMENT 'Was ausgeliehn wird, und Referenz, von wem, hier auch Adresse',
  `ausleiher_id` int(11) NOT NULL COMMENT 'Wer leiht es sich, Adresse hierrüber auch',
  `beginn` date NOT NULL COMMENT 'Wann',
  `enddatum` date NOT NULL COMMENT 'Bis wann',
  `rückgabe` date DEFAULT NULL COMMENT 'Wann es im angegebene Zeitraum zurückgegeben wurde',
  PRIMARY KEY (`leih_id`),
  KEY `ausleiher` (`ausleiher_id`),
  KEY `buch_id` (`buch_id`),
  CONSTRAINT `ausleiher` FOREIGN KEY (`ausleiher_id`) REFERENCES `nutzer` (`user_id`) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT `buch_id` FOREIGN KEY (`buch_id`) REFERENCES `buch_physisch` (`buch_id`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=13 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_uca1400_ai_ci;

-- Exportiere Daten aus Tabelle BuchAusleihApp.leihe_rückgabe: ~10 rows (ungefähr)
INSERT IGNORE INTO `leihe_rückgabe` (`leih_id`, `buch_id`, `ausleiher_id`, `beginn`, `enddatum`, `rückgabe`) VALUES
	(1, 1, 8, '2025-11-20', '2025-12-04', '2025-11-28'),
	(2, 2, 7, '2024-08-10', '2024-08-24', '0000-00-00'),
	(3, 3, 6, '2025-12-12', '2025-12-26', '2025-12-18'),
	(4, 4, 5, '2026-02-20', '2026-03-05', '0000-00-00'),
	(5, 5, 9, '2025-02-20', '2025-03-06', '2025-03-04'),
	(6, 6, 10, '2025-02-21', '2025-03-07', '0000-00-00'),
	(7, 7, 1, '2025-03-21', '2025-04-03', '0000-00-00'),
	(8, 8, 2, '2024-02-04', '2024-02-18', '2024-02-16'),
	(9, 9, 3, '2023-02-10', '2023-02-24', '2023-02-18'),
	(10, 10, 4, '2026-01-10', '2026-01-24', '0000-00-00');

-- Exportiere Struktur von Tabelle BuchAusleihApp.nutzer
CREATE TABLE IF NOT EXISTS `nutzer` (
  `user_id` int(11) NOT NULL AUTO_INCREMENT COMMENT 'Identifikation',
  `username` varchar(50) NOT NULL COMMENT 'UI sichtbar',
  `vorname` varchar(50) NOT NULL DEFAULT '' COMMENT 'Fürs Ver- und Ausleihen',
  `nachname` varchar(50) NOT NULL COMMENT 'Fürs Ver- und Ausleihen',
  `email` varchar(50) NOT NULL COMMENT 'Fürs Ver- und Ausleihen',
  `adresse_id` int(11) DEFAULT NULL COMMENT 'Fürs Ver- und Ausleihen, Referenz wo man wohnt',
  `password_hash` varchar(100) NOT NULL COMMENT 'Fürs Ver- und Ausleihen',
  PRIMARY KEY (`user_id`),
  KEY `adresse` (`adresse_id`),
  CONSTRAINT `adresse` FOREIGN KEY (`adresse_id`) REFERENCES `adresse` (`adress_id`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_uca1400_ai_ci;

-- Exportiere Daten aus Tabelle BuchAusleihApp.nutzer: ~10 rows (ungefähr)
INSERT IGNORE INTO `nutzer` (`user_id`, `username`, `vorname`, `nachname`, `email`, `adresse_id`, `password_hash`) VALUES
	(1, 'jdoe88', 'John', 'Doe', 'john.doe@example.com', 10, '$2y$10$vI8aWBnW3fID.L7W6GSRxeE15W/G9/ENF27E9F1R7R7R7R7R7R7R7'),
	(2, 'm_mustermann', 'Max', 'Mustermann', 'max.mustermann@test.de', 9, '67354zgfdhk685'),
	(3, 'annas', 'Anna', 'Schmidt', 'anna.schmidt@web.de', 8, 'fgdhjdfgzj7685648507izhjgf'),
	(4, 'tech_guru', 'Sarah', 'Wagner', 's.wagner@techmail.com', 7, 'dfgj78698679567iukjhzgkg'),
	(5, 'b_king', 'Bernd', 'König', 'bernd.koenig@mail.de', 6, '54w652zwhgfdk7645okl'),
	(6, 'lucky_luke', 'Lucas', 'Müller', 'l.mueller@provider.net', 5, 'fgdh34e53456rtzgherztdk6'),
	(7, 'marie_curie', 'Marie', 'Weber', 'm.weber@science.org', 4, 'hgfjl,uit8769549865ertujme'),
	(8, 'sunny99', 'Laura', 'Sonne', 'laura.sonne@sunshine.com', 3, '35876ertzsdfh24wq6437612'),
	(9, 'k_schulz', 'Kevin', 'Schulz', 'kevin.schulz@gmx.net', 2, 'fdgj65wsarzq5483iu7ik'),
	(10, 'boss_man', 'Thomas', 'Meyer', 't.meyer@business.de', 1, 'sdghjz7654i83ztrhertkl7465');

/*!40103 SET TIME_ZONE=IFNULL(@OLD_TIME_ZONE, 'system') */;
/*!40101 SET SQL_MODE=IFNULL(@OLD_SQL_MODE, '') */;
/*!40014 SET FOREIGN_KEY_CHECKS=IFNULL(@OLD_FOREIGN_KEY_CHECKS, 1) */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40111 SET SQL_NOTES=IFNULL(@OLD_SQL_NOTES, 1) */;
