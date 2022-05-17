from dataclasses import dataclass
from typing import Tuple

class Meta(type):
    def __new__(cls, name, bases, attrs):
        new_cls = super().__new__(cls, name, bases, attrs)
        return dataclass(unsafe_hash=True, frozen=True)(new_cls)


class Bio(metaclass=Meta):
    name        : str = "Krishnakanth Yachareni"
    designation : str = "Software Engineer Intern"
    company     : str = "Copart IT"
    base        : str = "Hattiesburg, Mississippi, USA"
    blog        : str = "https://krishnakanthyachareni.github.io/personal-website/"


class Stack(metaclass=Meta):
    languages   : Tuple[str, ...] = ("Java", "Python", "Javascript", "Shell")
    databases   : Tuple[str, ...] = ("MySQL", "PostgreSQL", "Oracle", "NoSQL")
    misc        : Tuple[str, ...] = ("Docker", "Kubernet")
    ongoing     : Tuple[str, ...] = ("Spring", "React", "Angular")


class Social(metaclass=Meta): 
    twitter     : str = "yacharenikrish"
    linkedin    : str = "yacharenikrishnakanth"
